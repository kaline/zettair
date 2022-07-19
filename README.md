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
..\zet -f porter -n 2 --summary capitalise "house AND cat"

```
![Screenshot_select-area_20220719184547](https://user-images.githubusercontent.com/31135896/179854133-b2535357-7e4e-40cf-ad03-6e2aa5b78378.jpg)


```
..\zet -f porter -n 2 --summary capitalise "apple AND banana"

```

![image](https://user-images.githubusercontent.com/31135896/179854231-e8de6292-cd51-4119-a03a-f2a65731667b.png)


### References

<p><a href="http://www.seg.rmit.edu.au/zettair/index.html">Zettair home page</a></p>
