# dzdzdz
java
  /**2. Добавить класс Team, который будет содержать название команды, массив из четырех участников (в конструкторе можно сразу указыватьвсех участников ), метод для вывода информации о членах команды, прошедших дистанцию, метод вывода информации обо всех членах команды.

3. Добавить класс Course (полоса препятствий), в котором будут находиться массив препятствий и метод, который будет просить команду пройти всю полосу;  **/
  добавляю пару участников
-------------------------------------------------------------------------------------------------------------------------
package Marathon;

public class Popugay extends Animal {
    public Popugay (String name) { super ("Попугай", name, 500, 5, 20); }
}
-------------------------------------------------------------------------------------------------------------------------
package Marathon;

public class Elephant extends Animal {
    public Elephant(String name) {
        super("Слон", name, 800, 50, 90); }
    }
-------------------------------------------------------------------------------------------------------------------------
package Marathon;

import java.util.Random;

public class Team {
private String nameTeam = " Heroes";
    Animal[] zverugi = {new Elephant("Летающий слон"), new Cat("Барсик"), new Dog("Бобик"), new Popugay("Кеша")} ;
    public Animal[] teamAnimal = new Animal[4];
    Random random = new Random();
    public Team(String nameTeam) {
        this.nameTeam = nameTeam;
        for(int i = 0; i < 4; i++)
        {
            int ran = random.nextInt(4);
            teamAnimal[i] = zverugi[ran];
        }
        //c.doIt(zverugi); // Просим команду пройти полосу
        //zverugi.showResults(); // Показываем результаты
         Team team = new Team("Winners", competitors);

        System.out.println(new team);
        System.out.println(team.getTeamName());
        team.showResults();

    }
}
---------------------------------------------------------------------------------------------------------------------------
package Marathon;

public class Course extends Main {
    Let[] let = new Let[3];
    Random random = new Random();

    public Course() {
        Track track = new Track(random.nextInt(100));
        Wall wall = new Wall(random.nextFloat()* 10);
        Water water = new Water(random.nextInt(100));
        let[0] = (Let) track;
        let[1] = (Let) wall;
        let[2] = (Let) water;
    }
    
    public void printInformationAboutTheObstacle() {
        System.out.println("Length track: " + ((Track) let[0]).getLength());
        System.out.println("Height wall: " + ((Wall) let[1]).getHeight());
        System.out.println("Length water: " + ((Water) let[2]).getLength());
        System.out.println();
    }

    public void passObstacles(Team team){
        for(Animal animal : team.teamAnimal){
            for(Let l : let){
                if(!l.doIt(animal)){
                    animal.setPassing(l.doIt(animal));
                    break;
                }
                animal.setPassing(true);
            }
        }
    }
}


