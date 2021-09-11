#include <stdio.h>
#include <math.h>
#define ON 1
#define OFF 0
unsigned char choice1=0,choice2=0,traffic_sensor=0,AC=OFF,Engine_Temp_Controller=OFF,engine=OFF,flag=0;
float Room_temp=24,Engine_temp=55,vehicle_speed=0;

void System_State(void) //Vehicle Control system menu
{
	do
	{
		printf("a. Turn on the vehicle engine\n");
		printf("b. Turn off the vehicle engine\n");
		printf("c. Quit the system\n\n");
		scanf(" %c",&choice1);
	}
	while((choice1 < 'a' || choice1 >'c')&&(choice1 < 'A' || choice1 >'C'));
}

void Sensor_Menu(void) //menu that simulates the vehicle sensors readings
{
	if(choice1 == 'a'||choice1 == 'A')
	{
		do
		{
			printf("a. Turn off the engine\n");
			printf("b. set the traffic light color\n");
			printf("c. set the room temperature\n");
			printf("d. set the engine temperature\n\n");
			scanf(" %c",&choice2);
		}
		while((choice2 < 'a' || choice2 >'d')&&(choice2 < 'A' || choice2 >'D'));
	}
}

void Display_State(void)  //Display the current vehicle state
{
	if(engine==ON)
	{
		printf("Engine is ON\n");
	}
	else if(engine == OFF)
	{
		printf("Engine OFF\n");
	}
	else
	{
		printf("error in Engine\n");
	}
	if(AC==ON)
	{
		printf("AC is ON\n");
	}
	else if(AC == OFF)
	{
		printf("AC is OFF\n");
	}
	else
	{
		printf("error in AC\n");
	}
	printf("vehicle speed = %f Km/hr \n",vehicle_speed);
	printf("Room temperature = %f Celsius \n",Room_temp);
	if(Engine_Temp_Controller == ON)
	{
		printf("Engine Temperature Controller is ON\n");
	}
	else if (Engine_Temp_Controller == OFF)
	{
		printf("Engine Temperature Controller is OFF\n");
	}
	else
	{
		printf("error in Engine Temperature Controller\n");
	}
	printf("engine temperature = %f Celsius \n\n",Engine_temp);
}

void Room_Temperature(void)
{
	printf("enter room temperature value\n");
	scanf("%f",&Room_temp);
	if(Room_temp < 10 || Room_temp > 30)
	{
		AC= ON;
		Room_temp=20;
	}
	else
	{
		AC = OFF;
	}
}

void Traffic_State(void)
{
	while(flag == 0)
	{
		printf("enter traffic status value (G or O or R)\n");
		scanf(" %c",&traffic_sensor);
		switch(traffic_sensor)
		{
		case 'G':
		case 'g':
			vehicle_speed =100;
			flag = 1;
			break;
		case 'O':
		case 'o':
			vehicle_speed =30;
			flag = 1;
			break;
		case 'R':
		case 'r':
			vehicle_speed = 0;
			flag = 1;
			break;
		default :
			flag = 0 ;
		}
	}
	flag = 0;
}

void Engine_Temperature(void)
{
	printf("enter engine temperature value \n");
	scanf("%f",&Engine_temp);
	if(Engine_temp<100 || Engine_temp>150)
	{
		Engine_Temp_Controller=ON;
		Engine_temp=125;
	}
	else
	{
		Engine_Temp_Controller=OFF;
	}
}


void Vehicle_Speed30(void)
{
	if(vehicle_speed==30)
	{
	AC=ON;
	Room_temp = Room_temp*((float)5/4)+1 ;
	Engine_Temp_Controller=ON;
	Engine_temp = Engine_temp*((float)5/4)+1;
	}
}

int main(){
	setvbuf(stdout, NULL, _IONBF, 0);
	setvbuf(stderr, NULL, _IONBF, 0);
	while(1){
	do{
		System_State();
		if (choice1 == 'b' || choice1 == 'B')
		{   engine=OFF;
			printf("the system is OFF\n\n");
		}
	}
	while(choice1 == 'b'||choice1 == 'B');

	if(choice1 == 'c' || choice1 == 'C')
	{
		printf("You Quit the system\n");
		break;
	}
	else if(choice1 == 'a'||choice1 == 'A')
	{
		engine=ON;
		printf("the system is ON\n\n");
		do{
			Sensor_Menu();
			if(choice2 == 'a' || choice2 == 'A')
			{
				engine=OFF;
			}
			else if(choice2 == 'b' || choice2 == 'B')
			{
				Traffic_State();
				Vehicle_Speed30();
				Display_State();
			}
			else if(choice2 == 'c' || choice2 == 'C')
			{
				Room_Temperature();
				Display_State();
			}
			else if(choice2 == 'd' || choice2 == 'D')
			{
				Engine_Temperature();
				Display_State();
			}

		}while(engine==ON);
	}
	}
	return 0;
}


