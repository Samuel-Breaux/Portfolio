# Portfolio
## Programming
### ELO Program 
Simple program written to practice basic object oriented programming skills
#### Player Class File
```
#include <cmath>
#include <iostream>
#include <fstream>
#include <sstream>
#include <vector>
using namespace std;

int k = 32;
class Player{
    private:
        int elo;
        string name;

    public:

        // Constructor to create a player or load an existing player by name
        Player(string nm) {
            if (!loadPlayer(nm)) {  // Try to load the player
                name = nm;
                elo = 800;
                savePlayer();  // Save the new player if not found
            }
        }

        // Constructor to create a player with a specific ELO rating or load existing player
        Player(string nm, int rating) {
            if (!loadPlayer(nm)) {  // Try to load the player
                name = nm;
                elo = rating;
                savePlayer();  // Save the new player if not found
            }
        }

        void setName(string nm){
            name = nm;
        }

        void setELO(int newELO){
            elo = newELO;
        }

        string getName(){
            return name;
        }

        int getELO(){
            return elo;
        }

        void displayInfo(){
            cout << getName() << ": " << getELO() << endl;
        }

       // Save player to file (update if player exists or add new player to file)
    void savePlayer() {
        vector<string> players;  // Vector to hold all players' data
        ifstream file("Players.txt");
        string line;
        bool playerExists = false;
        
        // Read all players and check for an existing player with the same name
        while (getline(file, line)) {
            string playerName = line; // First line is player name
            if (getline(file, line)) { // Second line is player ELO
                int playerElo = stoi(line);
                if (playerName == name) {
                    playerExists = true;
                    players.push_back(name + "\n" + to_string(elo));  // Update Elo for this player
                } else {
                    players.push_back(playerName + "\n" + to_string(playerElo)); // Insert old player data if no changes are needed
                }
            }
        }
        file.close();

        // If the player already exists, overwrite the file with updated data
        ofstream outFile("Players.txt", ios::trunc);  // Open in trunc mode to overwrite the file
        for (const string& playerData : players) {
            outFile << playerData << endl;
        }

        // If player didn't exist, append new player to the file
        if (!playerExists) {
            outFile << name << endl << elo << endl;
        }
        outFile.close();
    }

        bool loadPlayer(string playerName) {
            ifstream file("Players.txt");
            string line;
            bool playerFound = false;
    
            while (getline(file, line)) {
                string nameFromFile = line; //First line is player name
                cout << nameFromFile << endl;
                if (getline(file, line)) {  // Second line is player ELO
                    int eloFromFile = stoi(line);
                    if (nameFromFile == playerName) {
                        name = nameFromFile;
                        cout << name << " loaded from file" << endl;
                        elo = eloFromFile;
                        playerFound = true;
                        break;
                    }
                }
            }
            file.close();
            return playerFound;
        }

};

void eloCalculation(Player &A, Player &B, int AScore, int BScore){
    float expectedAScore = 1/(1+pow(10,(A.getELO()-B.getELO())/400));
    float expectedBScore = 1/(1+pow(10,(B.getELO()-A.getELO())/400));
    cout << "Expected A Score: " << expectedAScore << endl;
    cout << "Expected B Score: " << expectedBScore << endl;
    
    A.setELO(A.getELO() + k*(AScore - expectedAScore));
    B.setELO(B.getELO() + k*(BScore - expectedBScore));
    A.savePlayer();
    B.savePlayer();
}
```
#### Main File
```
#include <iostream>
#include <fstream>
#include "C:\Users\Intern Samuel\Desktop\C Workspace\ELO_Math.h"

using namespace std;



int main(){
    Player Player1 = Player("P1");
    Player Player2 = Player("P2");
    Player1.displayInfo();
    Player2.displayInfo();
    eloCalculation(Player1, Player2, 1, 0);
    Player1.displayInfo();
    Player2.displayInfo();

    return 0;
}
```
#### Save File
```
P1
816
P2
688
```
## CAD Work
### Final Project Fan Design
![Final Project Drawing](https://github.com/user-attachments/assets/ff8eaba7-9001-492f-a379-8945b36a60c3)
![Final Project Drawing (1)](https://github.com/user-attachments/assets/4202747f-6b8e-4473-b59b-5e5a283df8b4)
![Final Project Drawing (2)](https://github.com/user-attachments/assets/af035be5-4aa7-40d1-bb31-1db28757bce4)
![Final Project Drawing (3)](https://github.com/user-attachments/assets/f6b018b8-ae79-4ded-8537-398787639338)
![Final Project Drawing (4)](https://github.com/user-attachments/assets/990eaecd-c497-41f6-8b4b-569777ab32d0)
![Final Project Drawing (5)](https://github.com/user-attachments/assets/5006fc7f-1f95-452b-93d5-25ea726888f9)
![Final Project Drawing (6)](https://github.com/user-attachments/assets/7c3c4bec-75da-4fea-8617-7f0a7e840392)
![Final Project Drawing (7)](https://github.com/user-attachments/assets/8ba2a1a0-0e57-4386-8d7c-678f13235bf4)
