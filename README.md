# zettair
Activity of information retrieval 


### How to run

<p> Download the files to linux or windows. </p>

To linux run theses commands:
- 1 - ./configure --prefix=$HOME/local/zettair-0.9.3
- 2 - make
- 3 - make install 

### Run commands

#### The collection of documents
 
 - C:\Zettair\GH95
 - \Zettair\GH95
 
 Criação de índice,com zettair, chamado "índice1" da lista de arquivos: 
 
 ```
 ./zet -i -f indice1 --file-list lista_arquivos.txt 
```


 ![./zet -i -f indice1 --file-list lista_arquivos.txt ](https://user-images.githubusercontent.com/31135896/179834868-2a64b619-1410-4b23-896e-65d113c34e5e.jpg)
 
 
 ![image](https://user-images.githubusercontent.com/31135896/179841651-8ebd93d2-ec37-4c84-9371-fa1a8b429997.png)

 
 Criar um índice completo na indexação sem stemming:
 
 ```
 ./zet -i -f completo1 --big-and-fast --stem none --file-list lista_arquivos.txt
 ```
 
 ![./zet -i -f completo1 --big-and-fast --stem none --file-list lista_arquivos.txt](https://user-images.githubusercontent.com/31135896/179839883-96531cd7-7ad5-457b-a1c0-a91e09f002cb.jpg)

![image](https://user-images.githubusercontent.com/31135896/179841979-9a613a80-cde8-43fb-803c-f3630f04f910.png)

### Realizando consultas no modo interativo

```

zet -f <nome_do_índice> <consulta>

```
 
 ```
 
 ..\zet -f completo -n 10 "earthquake"
 
 ```
 

 ![ ..\zet -f completo -n 10 "earthquake"](https://user-images.githubusercontent.com/31135896/179851902-4824ad5a-33a2-4e96-8330-942c46046b3a.jpg)

```
..\zet -f porter -n 2 --summary capitalise "house cat"

```

![.\zet -f porter -n 2 --summary capitalise "house cat"](https://user-images.githubusercontent.com/31135896/179853439-88476d1f-57c0-46ed-93b8-a82817decce7.png)


```
..\zet -f porter -n 2 --summary capitalise "apple banana"

```

![image](https://user-images.githubusercontent.com/31135896/179853763-e6f55403-7397-4f6d-9e8c-208bd917cb9a.png)

```
..\zet -f porter -n 2 --summary capitalise "banana ak47"

```

![image](https://user-images.githubusercontent.com/31135896/179854442-28759726-2ce8-498e-bf88-822bba02a561.png)

```
..\zet -f porter -n 2 --summary capitalise "house AND cat"

```
![Screenshot_select-area_20220719184547](https://user-images.githubusercontent.com/31135896/179854133-b2535357-7e4e-40cf-ad03-6e2aa5b78378.jpg)


```
..\zet -f porter -n 2 --summary capitalise "apple AND banana"

```

![image](https://user-images.githubusercontent.com/31135896/179854231-e8de6292-cd51-4119-a03a-f2a65731667b.png)

```
..\zet -f porter -n 2 --summary capitalise "banana AND ak47"

```

![image](https://user-images.githubusercontent.com/31135896/179854628-73c97b54-6187-4bf1-9114-8d99f95c03e4.png)


### Executando consultas em lote

- Uso: ``` zet_trec -f <arquivo_de_topicos> <nome_do_indice> ```

Exemplo: ``` ..\zet_trec -f topicos05.txt porter ```
![..\zet_trec -f topicos05.txt porter](https://user-images.githubusercontent.com/31135896/179855233-df64419a-a658-48a9-86b9-05245785aefb.jpg)


```./zet_trec -t -d -f topicos05.txt -n 100 --okapi --query-stop stopwords.txt --big-and-fast -r okapi porter >saida_okapi.txt ```

 * Abaixo possíveis problemas no linux com a versão 0.9.3 do zettair:
 
 ![./zet_trec -t -d -f topicos05.txt -n 100 --okapi --query-stop stopwords.txt --big-and-fast -r okapi porter >saida_okapi.txt](https://user-images.githubusercontent.com/31135896/179855559-90ca20cb-320c-48b3-a1c9-6d925c5c10c9.png)


* Já que ocorreu o erro acima no linux, então a solução foi gerar as saídas no windows:

![image](https://user-images.githubusercontent.com/31135896/179858640-b4afdfa2-560f-41b9-b9ae-3b20cc0da2f0.png)

Para rodar o comando no linux, foi usado o dos2unix para converter o arquivo txt para formato unix:

``` dos2unix saida_okapi.txt ```

 Agora é possível verificar precisão do okapi:
 
 ``` trec_eval -c -o qrels_GH05.txt saida_okapi.txt  ```
 
![Screenshot_deepin-terminal_20220719193800](https://user-images.githubusercontent.com/31135896/179860122-ffcc4657-d092-470f-9210-57f34e4e5569.jpg)

 ``` trec_eval -c -o qrels_GH05.txt saida_cosine.txt  ```
 
![Screenshot_deepin-terminal_20220719195107](https://user-images.githubusercontent.com/31135896/179861476-7ff7f2c2-83ee-4ab3-8ac6-831b7aa62f2f.jpg)

 ``` trec_eval -c -o qrels_GH05.txt saida_default.txt  ```

![Screenshot_20220719201242](https://user-images.githubusercontent.com/31135896/179863550-9e214565-5bf2-4ed7-978a-e764e5fdff16.jpg)

 ``` trec_eval -c -o -q qrels_GH05.txt saida_okapi.txt  ```

![Screenshot_select-area_20220719215247](https://user-images.githubusercontent.com/31135896/179872492-646da58b-c615-4604-b5a8-d860a7e51880.jpg)


### References

<p><a href="http://www.seg.rmit.edu.au/zettair/index.html">Zettair home page</a></p>
