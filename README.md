# scrabble
scrabble game using C 

#include <cs50.h>
#include <ctype.h>
#include <stdio.h>
#include <string.h>

int main(void)
{

    int letters[26] = {1, 3, 3, 2,  1, 4, 2, 4, 1, 8, 5, 1, 3,
                       1, 1, 3, 10, 1, 1, 1, 1, 4, 4, 8, 4, 10};

    string words1 = get_string("Player 1: ");
    string words2 = get_string("Player 2: ");

    //  calculate scores

    int points1 = 0;
    int points2 = 0;

    // word1 loop
    for (int i = 0, n = strlen(words1); i < n; i++)
    {
        if (isalpha(words1[i]))
        {
            int index = toupper(words1[i]) - 'A';
            points1 += letters[index];
        }
    }

    // word2 loop
    for (int i = 0, n = strlen(words2); i < n; i++)
    {
        if (isalpha(words2[i]))
        {
            int index = toupper(words2[i]) - 'A';
            points2 += letters[index];
        }
    }

    // using conditionals to find out the winner
    if (points1 > points2)
    {
        printf("Player 1 wins!\n");
    }
    else if (points1 < points2)
    {
        printf("Player 2 wins!\n");
    }
    else
    {
        printf("Tie!\n");
    }
}
