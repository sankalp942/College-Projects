# College-Projects/movie-booking-project

//program to book movie ticikkets
//created by: Sankalp chhunchha
//time complexity: O(1)


#include<iostream>
#include<conio.h>
#include<cstdlib>
#include<time.h>
#include<string>
#include<unistd.h>


using namespace std;

string movieN,showT,locationT,priceM;
int a,b,c,d,e;
int ticketsN,totalM;

//to get movie name
int movieName(){
	int name;
	printf("Which Movie would you like to see?\n\n1.\tAvengers 4:Endgame\n2.\tIron Man 3\n3.\tIt:Chapter 2\n4.\t3 idiots\n\n");
	printf("enter the number of the movie name: ");
	scanf("%d",&name);
	printf("\n");
	return name;
}

//to get show timing
int showTiming(){
	int timing;
	printf("\nSelect Timing:\n\n1.\t9:15AM\n2.\t12:15PM\n3.\t3:15PM\n4.\t6:15PM\n\n");
	printf("Enter timing here: ");
	scanf("%d",&timing);
	cout<<"\n";
	return timing;
}

//to get number of ticikets
int numberOfTickets(){
	int persons;
	printf("Enter how many tickets you want to book: ");
	scanf("%d",&persons);
	return persons;
}

//price of seat class
int priceOfMovie(){
	int price;
	printf("1.Balcony class:140/-\n2.Premium class:200/-\n");
	printf("Which class would you like to book: ");
	scanf("%d",&price);
	return price;
}

//to get location
int location(){
	int place;
	printf("\nWhere do you want to see your movie ");
	printf("\n1.\tPVR Transcube\n2.\tPVR SG Highway\n3.\tHansraj cinema Ranip\n\n");
	printf("enter the number of place:  ");
	scanf("%d",&place);
	return place;	
}

//this will calculate the total price of ticikets
int totalPrice(int e){
	if(e==1){
		for(int i=1;i<=ticketsN;i++){
		totalM+=140;
		}
		return totalM;
	}
	else if(e==2){
		for(int i=1;i<=ticketsN;i++){
		totalM+=200;
		}
		return totalM;
	}
//	else(){
//	totalM=0;
//	}
}

//this will return movie name as per condition
string getMovieName(int b){
A:	switch(b){
			case (1):
				return movieN="Avengers 4";
				break;	
			case 2:
				return movieN="Iron Man 3";
				break;
			case 3:
				return movieN="It: Chapter 2";
				break;
			case 4:
				return movieN="3 idiots";
				break;
			default:
				 cout<<"invalid input\n";
				 exit(-1);
				 break;
			} 
}

//this will return show timings
string getShowTime(int c){
B:	switch(c){
			case 1:
				return showT="9:15";
				break;
			case 2:
				return showT="12:15";
				break;
			case 3:
				return showT="3:15";
				break;
			case 4:
				return showT="6:15";
				break;
			default:
				cout<<"\nInvalid input\n";
				break;
			}
}

//this will return location 
string getTlocation(int d){
C:	switch(d){
			case 1:
				return locationT="PVR Transcube";
				break;
			case 2:
				return locationT="PVR SG Highway";
				break;
			case 3:
				return locationT="Hansraj cinema Ranip";
				break;
			default:
				cout<<"\nInvalid input";
				break;
				
			}
}

//this will return string value of price of seat class
string getPriceOfMovie(int e){
D:	switch(e){
			case 1:
				return priceM="Baclony Class: 140/-";
				break;
			case 2:
				return priceM="Premium Class: 200/-";
				break;
			default:
				cout<<"\nInvalid input";
				break;
			}
}

//the main function where the program starts to get executed
int main(){
	string mName,sTime,mLocation;
	int Q;
		do{
		
		b=movieName();				//b will contain the value returned by movieName function
		mName=getMovieName(b);			//mName will store the movie name
		c=showTiming();				//c will store the value returned by showTiming
		sTime=getShowTime(c);			//sTime will store the timing
		e=priceOfMovie();			//e will show price of movie
		P=getPriceOfMovie(e);			//this will store price value
		ticketsN= numberOfTickets();		//this will store the number of ticikets
		d=location();				//d will store the location value returned by location
		mLocation=getTlocation(d);		//this will store the string value returned by getLocation
		Q=totalPrice(e);			//this will call the totalPrice function to calculate total price

		cout<<"please wait while we book tickets...";
		cout.flush();
		usleep(30000);				//this will make the process sleep for 3 seconds
		cout<<"\nHurray!! you have booked "<<mName<<" at timing "<<sTime<<" at "<<P<<" for "<<ticketsN<<" at "
		<<mLocation<<"\n";
		cout<<" Total value: "<<Q<<"/-\n";
		cout<<"press 0 to exit and 1 to re-book a movie:\n";		//press 0 to EXIT and 1 to BOOK-AGAIN
		cin>>a;
		if(a==0)
			exit(1);
		
		}while(a=1);

}
