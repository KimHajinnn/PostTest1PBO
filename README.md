# PostTestPBO
Nama    : Christian Amsal Asimaro Lumban Tobing

NIM     : 2409116053

package com.mycompany.posttest1;

import java.util.ArrayList;
import java.util.Scanner;

public class PostTest1 {
    static class Manhwa {
        String Title;
        String Author;
        int Chapter;
        String Genre;
        String Status;
        
        Manhwa(String Title, String Author, int Chapter, String Genre, String Status){
            this.Title = Title;
            this.Author = Author;
            this.Chapter = Chapter;
            this.Genre = Genre;
            this.Status = Status;
        }
    }
    
    public static void main(String[] args) {
        ArrayList<Manhwa> DaftarManhwa = new ArrayList<>();
        Scanner input = new Scanner(System.in);
        int Menu;
        
        DaftarManhwa.add(new Manhwa("Solo Leveling", "Chugong", 179, "Action/Adventure/Fantasy", "Completed"));
        DaftarManhwa.add(new Manhwa("Omniscient Readers Viewpoints", "Redice Studio", 278, "Action/Adventure/Fantasy", "Ongoing"));
        DaftarManhwa.add(new Manhwa("The Novel’s Extra (Remake)", "Jee Gab Song", 142, "Action", "Ongoing"));
        DaftarManhwa.add(new Manhwa("Revenge of the Iron-Blooded Sword Hound", "I Stepped On Lego", 129, "Action/Adventure/Fantasy/Martial Arts/Supernatural", "Ongoing"));
        
        do {            
            System.out.println("=== Option Manhwa Online ===");
            System.out.println("1. Add new Manhwa");
            System.out.println("2. Show List Manhwa");
            System.out.println("3. Update Manhwa Chapters");
            System.out.println("4. Delete Manhwa");
            System.out.println("5. Leave Program");
            System.out.print("Select Menu : ");
            Menu = input.nextInt();
            input.nextLine();
            
            switch(Menu) {
                case 1:
                    System.out.print("Input Manhwa Title: ");
                    String Title = input.nextLine();
                    System.out.print("Input Manhwa Author: ");
                    String Author = input.nextLine();
                    System.out.print("Input Manhwa Chapter: ");
                    int Chapter = input.nextInt();
                    System.out.print("Input Manhwa Genre: ");
                    String Genre = input.nextLine();
                    System.out.print("Input Manhwa Status: ");
                    String Status = input.nextLine();
                    DaftarManhwa.add(new Manhwa(Title, Author, Chapter, Genre, Status));
                    System.out.println("New Manwha Success added!!");
                    break;
                    
                case 2:
                    System.out.println("=== Manhwa List ===");
                    if (DaftarManhwa.isEmpty()) {
                        System.out.println("Manhwa List is Empty");
                    } else{
                        for (int i = 0; i < DaftarManhwa.size(); i++) {
                            Manhwa Number = DaftarManhwa.get(i);
                            System.out.println("-----------------------------------");
                            System.out.println("No          : " + (i + 1));
                            System.out.println("Title       : " + Number.Title);
                            System.out.println("Author      : " + Number.Author);
                            System.out.println("Chapter     : " + Number.Chapter);
                            System.out.println("Genre       : " + Number.Genre);
                            System.out.println("Status      : " + Number.Status);
                            System.out.println("-----------------------------------");
                        }
                    }
                    break;
                    
                case 3:
                    System.out.println("=== Update Manhwa Chapter ===");
                    if (DaftarManhwa.isEmpty()) {
                        System.out.println("Manhwa List is Empty");
                    } else {
                        for (int i = 0; i < DaftarManhwa.size(); i++) {
                            Manhwa Number = DaftarManhwa.get(i);
                            System.out.println("-----------------------------------");
                            System.out.println("No          : " + (i + 1));
                            System.out.println("Title       : " + Number.Title);
                            System.out.println("Author      : " + Number.Author);
                            System.out.println("Chapter     : " + Number.Chapter);
                            System.out.println("Genre       : " + Number.Genre);
                            System.out.println("Status      : " + Number.Status);
                            System.out.println("-----------------------------------");
                        }
                        System.out.print("Select Manhwa Number: ");
                        int indexUpdate = input.nextInt();
                        input.nextLine();
                        if (indexUpdate > 0 && indexUpdate <= DaftarManhwa.size()) {
                            Manhwa PickManhwa = DaftarManhwa.get(indexUpdate - 1);
                            
                            System.out.println("---------------------------");
                            System.out.println("1. Update Manhwa Title");
                            System.out.println("2. Update Manhwa Author");
                            System.out.println("3. Update Manhwa Chapter");
                            System.out.println("4. Update Manhwa Genre");
                            System.out.println("5. Update Manhwa Status");
                            System.out.println("---------------------------");
                            System.out.print("Select Manhwa Update: ");
                            int OptionUpdate = input.nextInt();
                            input.nextLine();
                            
                            switch (OptionUpdate) {
                                case 1:
                                    System.out.print("Input New Manhwa Title: ");
                                    PickManhwa.Title = input.nextLine();
                                    System.out.println("Update Manhwa Title Success");
                                    break;
                                case 2:
                                    System.out.print("Input New Manhwa Author: ");
                                    PickManhwa.Author = input.nextLine();
                                    System.out.println("Update Manhwa Author Success");
                                    break;
                                case 3:
                                    System.out.print("Input New Manhwa Chapter: ");
                                    PickManhwa.Chapter = input.nextInt();
                                    input.nextLine();
                                    System.out.println("Update Manhwa Chapter Success");
                                    break;
                                case 4:
                                    System.out.print("Input New Manhwa Genre: ");
                                    PickManhwa.Genre = input.nextLine();
                                    System.out.println("Update Manhwa Genre Success");
                                    break;
                                case 5:
                                    System.out.print("Input New Manhwa Status: ");
                                    PickManhwa.Status = input.nextLine();
                                    System.out.println("Update Manhwa Status Success");
                                    break;
                                default:
                                    System.out.println("Update Invalid");
                            }
                        } else {
                            System.out.println("Number Invalid");
                        }
                    }
                    break;
                    
                case 4:
                    System.out.println("=== Delete Manhwa Data ===");
                    if (DaftarManhwa.isEmpty()) {
                        System.out.println("Manhwa List is Empty");
                    } else {
                        for (int i = 0; i < DaftarManhwa.size(); i++) {
                            Manhwa Number = DaftarManhwa.get(i);
                            System.out.println("-----------------------------------");
                            System.out.println("No          : " + (i + 1));
                            System.out.println("Title       : " + Number.Title);
                            System.out.println("Author      : " + Number.Author);
                            System.out.println("Chapter     : " + Number.Chapter);
                            System.out.println("Genre       : " + Number.Genre);
                            System.out.println("Status      : " + Number.Status);
                            System.out.println("-----------------------------------");
                        }
                        System.out.print("Select Manhwa to Delete: ");
                        int DeleteIndex = input.nextInt();
                        input.nextLine();
                        if (DeleteIndex > 0 && DeleteIndex <= DaftarManhwa.size()) {
                            DaftarManhwa.remove(DeleteIndex - 1);
                            System.out.println("Delete Manhwa Data Success");
                        } else {
                            System.out.println("Number Invalid");
                        }
                    }
                    break;
                    
                case 5:
                    System.out.println("Leaving Program!!");
                    System.out.println("Thankyou <3");
                    break;
                    
                default:
                    System.out.println("Option Invalid, Try Again!!");
            }
        } while (Menu !=5);
        
        input.close();
    }
}
