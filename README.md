# Codealpha__CGPA
#include <iostream>
#include <vector>
#include <iomanip>
using namespace std;

int main() {
    int numCourses;
    cout << "Enter the number of courses: ";
    cin >> numCourses;

    vector<float> grades(numCourses);
    vector<float> credits(numCourses);

    float totalGradePoints = 0;
    float totalCredits = 0;

    // Taking input for each course
    for (int i = 0; i < numCourses; i++) {
        cout << "\nEnter grade for course " << i + 1 << ": ";
        cin >> grades[i];

        cout << "Enter credit hours for course " << i + 1 << ": ";
        cin >> credits[i];

        totalGradePoints += grades[i] * credits[i];
        totalCredits += credits[i];
    }

    // Calculating CGPA
    float cgpa = totalGradePoints / totalCredits;

    // Displaying results
    cout << "\nCourse-wise details:\n";
    for (int i = 0; i < numCourses; i++) {
        cout << "Course " << i + 1 << ": Grade = " << grades[i]
             << ", Credit = " << credits[i] << endl;
    }

    cout << fixed << setprecision(2);  // To show CGPA up to 2 decimal places
    cout << "\nFinal CGPA: " << cgpa << endl;

    return 0;
}
