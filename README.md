	Algoritmo MezclaEntreDosVectoresOrdenados
	//Definimos las estructuras de datos
	Definir tam_max Como Entero
	//Tamaño maximo del vector
	tam_max <- 6
	Definir v1,v2,v3 Como Entero
	Dimension v1[tam_max], v2[tam_max], v3[tam_max+tam_max]
	//Cantidad de elementos de los vectores (en el ejemplo será 6)
	
	n1 <- 0 //numero de elementos actuales de v1
	n2 <- 0 //numero de elementos actuales de v2
	n3 <- 0 //numero de elementos actuales de v3
	
	//Rellenamos los valores del vector v1
	Para i <- 1 hasta tam_max Hacer
		Leer v1[i]
		n1 <- n1+1		
	FinPara
	
	//Rellenamos los valores del vector v2
	Para j <- 1 hasta tam_max Hacer
		Leer v2[j]
		n2 <- n2+1		
	FinPara
	
	//Realizaremos la ordenacion de los vectores de v1	
	ordenado <- falso
	Mientras ordenado = falso Hacer
		ordenado <- verdadero
		Para j<-1 hasta n1-1 Hacer
			Si v1[j]>v1[j+1] Entonces
				//Haremos el intercambio
				aux <- v1[j]
				v1[j] <- v1[j+1]
				v1[j+1] <- aux
				//mientras sigo intercambiando, no esta ordenado
				ordenado <- falso
			FinSi			
		FinPara
	FinMientras
	
	//Mezclaremos (fusionaremos) los valores de v1 y v2 en v3
	
	i <- 1 //apuntamos al primer elemento de  v1
	j <- 1 //apuntamos al primer elemento de  v1
	k <- 0 //apuntamos a "ningún" (inexistente) elemento de v3 porque aún no sabemos cuál es (a diferencia de v1 y v2 que sí son vectores rellenados)
	
	Mientras  i <= n1 y j <= n2 Hacer
		Si v1[i]< v2[j] Entonces
			k <-k+1
			//Copiamos el elemento a v3
			v3[k]<-v1[i]
			i<-i+1
		SiNo
			k <-k+1
			//Copiamos el elemento a v3
			v3[k]<-v2[j]
			j<-j+1	
		FinSi
	FinMientras
	
	//Que pasa si v1 o v2 han llegado al fin
	
	Mientras  i <= n1 Hacer
		//Lo que sobra  de v1 lo añadimos a v3
		k <-k+1
		v3[k]<-v1[i]
		i<-i+1
	FinMientras
	
	Mientras  j <= n2 Hacer
		//Lo que sobra  de v1 lo añadimos a v3
		k <-k+1
		v3[k]<-v2[j]
		j<-j+1
	FinMientras
	n3<-k
	
	Escribir "elementos de V3"
	Para k<-1 hasta n3 Hacer
		Escribir v3[k]
	FinPara
	
FinAlgoritmo
