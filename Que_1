#include <iostream>

#include <bits/stdc++.h>

using namespace std;

float areaOfTriangle(int, int, int, int, int, int);
double polygonArea(double[], double[], int);
bool isInside(double[], double[][2], int);

int main() {
  /*********Test_Case_1**********/
  cout << "Test_Case_1:" <<endl;

  double P1[2] = { 3, 5 };
  double polygon1[4][2] = { { 1 , 0 }, { 8, 3 }, { 8, 8 }, { 1, 5 } };
  int totalPoints1 = sizeof(polygon1) / sizeof(polygon1[0]);
  if (isInside(P1, polygon1, totalPoints1))
      cout << "Point lies inside the polygon" << endl;
  else
      cout << "Point is outside the polygon" << endl;

  /*********Test_Case_2**********/
  cout << "\nTest_Case_2:\n";
  double P2[2] = { 0, 0 };
  double polygon2[5][2] = { { -3, 2 }, { -2, -0.8 }, { 0, 1.2 }, { 2.2, 0 }, { 2, 4.5 } };
  int totalPoints2 = sizeof(polygon2) / sizeof(polygon2[0]);
  if (isInside(P2, polygon2, totalPoints2))
      cout << "Point lies inside the polygon" << endl;
  else
      cout << "Point is outside the polygon" << endl;
}


/* isInside
 **  returns that point is inside polygon or not 
 **  Arguments: double point[2], double polypoints[][2], int size
 ** returns true if point is inside the polygon else return false
 */
bool isInside(double point[], double polyPoints[][2], int size) {
  double xCoordinates[size];
  double yCoordinates[size];

  for (int index = 0; index < size; index++) {
    xCoordinates[index] = polyPoints[index][0];
    yCoordinates[index] = polyPoints[index][1];

  }

/*calculating the individual area for point P
**taking the co-ordinates of P along with co-ordinates of two other Points
**which will make the triangle 
**so finding the area of each triangle
**if point lies inside the polygon or on the edge then sum of 
**individual area and polygon area will be same
**if sum of individual area eqaul to polygon area it will return true else false
*/
  double individualAreaSum = 0.0;

  int j = size - 1;
  for (int i = 0; i < size; i++) {
    individualAreaSum+= areaOfTriangle(point[0], point[1], xCoordinates[j], yCoordinates[j], xCoordinates[i], yCoordinates[i]);
    j = i; 
  }

  return (individualAreaSum == polygonArea(xCoordinates, yCoordinates, size));
}


/*calculating the entire area of polygon
**using shoelace formula
**return the absolute value
*/
double polygonArea(double X[], double Y[], int n) {

  double area = 0.0;

  int j = n - 1;
  for (int i = 0; i < n; i++) {
    area += (X[j] + X[i]) * (Y[j] - Y[i]);
    j = i; 
  }
  
  return abs(area / 2.0);
}

//function to calculate the area of triangle
float areaOfTriangle(int x1, int y1, int x2, int y2, int x3, int y3) {
  return abs((x1 * (y2 - y3) + x2 * (y3 - y1) + x3 * (y1 - y2)) / 2.0);
}
