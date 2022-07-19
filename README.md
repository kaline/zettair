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
 
 Criação: ./zet -i -f indice1 --file-list lista_arquivos.txt 

 ![Screenshot_deepin-terminal_20220719164135](https://user-images.githubusercontent.com/31135896/179834868-2a64b619-1410-4b23-896e-65d113c34e5e.jpg)
 
 Criar um índice completo na indexação sem stemming:
 
 ./zet -i -f completo --big-and-fast --stem none --file-list lista_arquivos.txt
 ![./zet -i -f completo --big-and-fast --stem none --file-list lista_arquivos.txt](https://user-images.githubusercontent.com/31135896/179839883-96531cd7-7ad5-457b-a1c0-a91e09f002cb.jpg)


### References

<p><a href="http://www.seg.rmit.edu.au/zettair/index.html">Zettair home page</a></p>
