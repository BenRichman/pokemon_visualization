# Learning to Become a Pokemon Trainer 

To view the interactive plots you can check the Python notebook at - 
[NB Viewer Jupyter Notebook]( http://nbviewer.jupyter.org/github/BenRichman/pokemon_visualization/blob/f7418350db12c2d7415c5a9180a29f56d095403f/Notebook/pokemon_analysis.ipynb)

## Summary
Since the Pokemon franchise was rejuvenated with the highly popular mobile Pokemon GO game, I was reminded of first learning to play Pokemon in Pokemon Red and Blue. Learning the game before online guides was difficult and included a lot of guesswork – what type is this Pokemon? What is super effective against it? Is this Pokemon strong or weak?

This analysis is geared towards providing a new Pokemon trainer with the tools to become a Pokemon master. Becoming a Pokemon master requires knowledge of all the Pokemon that you will attempt to catch or battle – all of their battle statistics (e.g. Attack, Defense) and typing (e.g. Grass, Water), and these introductory features are visualized and analyzed in the notebook. This notebook will visualize each of the 18 Pokemon types, display their battle statistics, identify the strongest and weakest Pokemon, predict battle outcomes, and provide the trainer with a Pokedex: a tool for accessing battle statistics of individual Pokemon. 

## Getting Started
In this Github, there is a Python notebook titled pokemon_analysis.ipynb with details on the cleaning and analysis, and the production of the graphs and images. The corresponding datasets are also uploaded as .csv files. There is another folder named icons with optional Pokemon sprites. They are not necessary for the notebook to run but add the sprites to the Pokedex at the end of the notebook. 

### Prerequisites/Tech Stack
The following software is required for completing the notebook:
    pandas, numpy, seaborn, matplotlib, plotly, sci-kit learn.
Each package can be installed through pip installation (https://packaging.python.org/tutorials/installing-packages/) or some packages are available to install through package managers built into software like Canopy or Anaconda. 
All packages function best in the latest update of Python 3. 

If you are unfamiliar with working with dataframes, seaborn, plotly or matplotlib, it is recommended to refresh yourself on those packages before moving forward. Sci-kit learn is a machine learning package and its usage is kept in its own section as it has a steeper learning curve.

### Background
This analysis is based off the Pokemon video games – a set of role-playing games licensed by the Nintendo Corporation brought to America on September 12, 1998. In the games, the objective is to become a Pokemon master; a Pokemon trainer that has reached the peak of the training world. Becoming a Pokemon master requires knowledge of all the Pokemon that you will attempt to catch or battle – all of their battle statistics (e.g. Attack, Defense) and typing (e.g. Grass, Water), and these introductory features are visualized and analyzed in the notebook. 

There are three datasets included: Pokemon characteristics, Pokemon combats, and a general Pokemon dataset.  

The important columns in Pokemon characteristics are the identification characteristics (number and name), typing (Type_1, Type_2), battle statistics (Total to Speed), and Generation.

The three columns in Pokemon combats describe which Pokemon were involved in the battle and who won. The general Pokemon dataset is used to merge with the combats to identify the names of the Pokemon in the battles since the numbers are different between the characteristics dataset and the combats dataset. 

### Common Pokemon Types
To visualize the 18 different types and the popularity of those types as primary or secondary types, I plotted the counts of the types as a stacked horizontal bar plot. Each type is color coded to have a representative color as the primary typing, and a darker shade for the secondary typing. 

![alt text][logo]

[logo]: https://github.com/BenRichman/pokemon_visualization/blob/master/images/Pokemon_types_count.png "Most Common Pokemon Types"

The four most popular types are also easy types to encounter – water, normal, flying, and grass, which all can be encountered in any generic water or on any generic land. The least common types are types that were introduced in later Generations (fairy, steel and dark), or are commonly legendary like dragon. Ghost and ice types are found in more gimmicky parts of the games, so are less common. 

As a Pokemon trainer, this information better informs what types of Pokemon you should expect to encounter on your journey. In addition, because the goal is to  catch the best ones and battle them, any good Pokemon team must have Pokemon suitable to battling the most common Pokemon types. 

### Distribution of Battle Statistics 

![alt text][logo1]

[logo1]: https://github.com/BenRichman/pokemon_visualization/blob/master/images/battle_stats_boxplot.png "Distribution of Battle Statistics"

Although the median value of each of the 6 battle statistics (hit points, attack, defense, special attack, special defense, and speed) is approximately equal, the distribution of each tells an interesting story. 

Overall, defensive characteristics have more outliers than offensive characteristics. Defensive characteristics are HP, defense, and special defense and the boxplot shows significantly more outliers on the upper end for these features. This suggests that it is harder to predict defensive qualities of Pokemon than offensive qualities. As a budding Pokemon trainer, be prepared to defend against predictable offensive qualities, but also when you are on the offensive to prepare in case you meet an unpredictably strong defensive Pokemon. 


![alt text][logo2]

[logo2]: https://github.com/BenRichman/pokemon_visualization/blob/master/images/stats_corr_heatmap.png "Battle Statistics Correlations Heatmap"

The correlations between different Pokemon battle statistics provide information on the common battle statistics groups. High correlations indicate that those are common pairings and split the Pokemon into 5 basic battle groups:
1.	Overall defensive Pokemon that have high defense and special defense
2.	Special Pokemon with high special attack and special defense
3.	Physical Pokemon with high Attack and Defense
4.	Fast special attackers
5.	Strong physical attackers with high HP
It should be notably rare then, to find a Pokemon with high attack and special defense, or high special attack and high defense. To best battle attack minded Pokemon, try attacking physical Pokemon with special moves and special Pokemon with physical moves. 

### Predicting Battle Outcomes

![alt text][logo3]

[logo3]: https://github.com/BenRichman/pokemon_visualization/blob/master/images/battle_prediction.png "Battle Prediction Algorithms"

Using just information on each Pokemon’s  base stats and their legendary status, I employed a variety of classification algorithms to both test each one’s accuracy, as well as the limits of the overall accuracy in battle prediction. Random Forest, Decision Tree and Gradient Boosting compose the 3 most accurate algorithms, with an accuracy around 90%. 

### Pokedex

![alt text][logo4]

[logo4]: https://github.com/BenRichman/pokemon_visualization/blob/master/images/pokedex.png "Pokedex: Pikachu"

A Pokedex is a device in the main Pokemon video games that allows a Pokemon trainer to search for a Pokemon and receive important information on that Pokemon. In this Pokedex, a Pokemon trainer can search by either the Pokedex number a Pokemon is stored in, or by the Pokemon name. 

The output is a bar chart that highlights in green the base battle stat(s) that are highest for a Pokemon and provides a sum of the base stats to give an overall idea of how strong the Pokemon is. Because true numbers are dependent on extra information such as what level the opposing Pokemon is, the ‘base stats’ are used to compare average relative strengths of Pokemon at the same level. In real battles, take care of your relative levels as they will influence the damage taken and received. 

### Conclusion

Now you have a foundational understanding of Pokemon so you can begin you journey. You’ve mastered common typing, understand the difference in outlier behavior between offensive and defensive statistics,  battle statistic distributions, Pokemon battle types, can predict the winner of a battle, and have your very own Pokedex, your (well prepared) journey can finally begin. 
