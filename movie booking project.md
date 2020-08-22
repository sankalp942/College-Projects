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

string movieN,showT,locationT;
int a,b,c,d;
int ticketsN;

int movieName(){
	int name;
	printf("Which Movie would you like to see?\n\n1.\tAvengers 4:Endgame\n2.\tIron Man 3\n3.\tIt:Chapter 2\n4.\t3 idiots\n\n");
	printf("enter the number of the movie name: ");
	scanf("%d",&name);
	printf("\n");
	return name;
}

int showTiming(){
	int timing;
	printf("\nSelect Timing:\n\n1.\t9:15AM\n2.\t12:15PM\n3.\t3:15PM\n4.\t6:15PM\n\n");
	printf("Enter timing here: ");
	scanf("%d",&timing);
	cout<<"\n";
	return timing;
}

int numberOfTickets(){
	int persons;
	printf("Enter how many tickets you want to book: ");
	scanf("%d",&persons);
	return persons;
}

int location(){
	int place;
	printf("\nWhere do you want to see your movie ");
	printf("\n1.\tPVR Transcube\n2.\tPVR SG Highway\n3.\tHansraj cinema Ranip\n\n");
	printf("enter the number of place:  ");
	scanf("%d",&place);
	return place;	
}

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

int main(){
	string mName,sTime,mLocation;
		do{
		
		b=movieName();
		mName=getMovieName(b);
		c=showTiming();
		sTime=getShowTime(c);
		ticketsN= numberOfTickets();
		d=location();
		mLocation=getTlocation(d);
		cout<<"please wait while we book tickets...";
		cout.flush();
		usleep(30000);
		cout<<"\nHurray!! you have booked "<<mName<<" at timing "<<sTime<<" for "<<ticketsN<<" at "
		<<mLocation<<"\n";
		cout<<"press 0 to exit and 1 to re-book a movie:\n";
		cin>>a;
		if(a==0)
			exit(1);
		
		}while(a=1);

}

