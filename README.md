#include <iomanip>
#include <iostream>
#include <string>
#include <sstream>
#include <vector>
#include <fstream>

using namespace std;

//display reports
class display 
{
public:
	display(
		int year,
		string make,
		string model,
		string usedOrNew,
		int price,
		int consumerRating
	){
		Year = year;
		Make = make;
		Model = model;
		uON = usedOrNew;
		Price = price;
		ConsumerRating = consumerRating;
	}
	
	
		
		
	void result() {
		cout << " Year: " << Year << endl;
		cout << " Make " << Make << endl;
		cout << " Model: " << Model << endl;
		cout << " User or New: " << uON << endl;
		cout << " Price: " << Price << endl;
		cout << " ConsumerRating: " << ConsumerRating << endl;
		
		cout << endl;



	}

	
	int Year;
	string Make;
	string Model;
	string uON;
	int Price;
	int ConsumerRating;
	
};



int main()
{
	
	ifstream infile;
	infile.open("C:\\temp\\Car_Sales.csv");

	vector <display> cars;
	

	string line = "";
	getline(infile, line);
	line = "";
	while (getline(infile, line))
	{
		int year;
		string make;
		string model;
		string usedOrNew;
		int price;
		string consumerRating;
		string tempStr = "";

		stringstream input(line);

		getline(input, tempStr, ',');
		year = atoi(tempStr.c_str());
		
		getline(input, make, ',');
		getline(input, model, ',');
		getline(input, usedOrNew, ',');

		
		getline(input, tempStr, ',');
		price = atoi(tempStr.c_str());

		
		
		getline(input, consumerRating, ',');

		
		


		display cars(year, make, model, usedOrNew, price, consumerRating);

		
		

		line = "";
	}


	for (auto cars : cars) {
		cars.result();
	}



