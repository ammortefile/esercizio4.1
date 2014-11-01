
 #include<iostream>
 using namespace std;
 int main()
 {
   int T[100];
   int P[10];
   int dimT;
   int dimP;
   int N=0,x=0,y=0, matchN=0,matchS=0; 
   bool bolt=true;
   bool bolp=false;
   int z,H,q,w;

   cout<<"inserisci dimensione dimT= ";
   cin>>dimT;
   cout<<"inserisci dimensione dimP= ";
   cin>>dimP;
  	
 	 while(dimT > 100 || dimT<1){
 	cout<<"dimT deve avere una dimensione da 1 a 100"<<endl;
 	cout<<"Reinserisci dimensione dimT= ";
 	cin>>dimT;
 			  }				//Pre= (cin 0<dimT<=100  &&  0<dimP<=10, seguito da dimT interi && dimP interi)

 while (dimP > 10 || dimP<1){
 cout<<"dimP deve avere una dimensione da 1 a 10"<<endl;
 cout<<"Reinserisci dimensione dimP= ";
 cin>>dimP;
 cout<<"Reinserisci dimensione dimT= ";
 cin>>dimT;
 }

   while (dimP > dimT){
          cout<<"La dimensione di (dimT) deve essere maggiore della dimensione (dimP),"<<endl;
	  cout<<"perfavore reinserisci la dimensione di dimT = "<<endl;
          cin>>dimT;
 	 }


  while(N<dimT && bolt)  //ciclo che inserisce da cin in T
  {

     cout<<"inserisci Numeri in T= ";
     cin>>z;
     T[N]=z;	 
     N++;               
  }				


 bolp=true;
 N=0;
        while(N<dimP && bolp){
        cout<<"inserisci Numeri in P= ";
        cin>>H;			//ciclo che inserisce da cin in P
        P[N]=H;                 
        N++;                   }
       
     
     
    do{		//ciclo match non sovrapposti
  
     if(T[x]==P[y]){  
		x++;
		y++;
		   }
      
                  else {x++; y=0;} 

	if(y==dimP){matchN++; y=0;}		
      }
      while (x<=dimT);
       
 x=0; y=0;

  do{		//ciclo match  sovrapposti
  
     if(T[x]==P[y]){  
		x++;
		y++;
		   }
      
                  else {x++; y=0;} 

	if(y==dimP){matchS++; y=0; x=x-2;}		
      }
      while (x<=dimT);
		  

 cout<<"Match Trovati (NON SOVRAPPOSTI)= "<< matchN<<endl;
 cout<<"Match Trovati  (SOVRAPPOSTI)= "<< matchS<<endl;
 						//POST=()	
 }
