# AddressBook

package com.mycompany.addresbook;

import java.io.BufferedReader;
import java.io.BufferedWriter;
import java.io.FileReader;
import java.io.FileWriter;
import java.util.HashMap;
import java.util.Map;
import java.util.Scanner;

public class adrressBook {
    
    private Map<String, String> conts;
    private String filePath;
    
    public adrressBook(String filePatch){
        
        this.conts = new HashMap<>();
        this.filePath = filePatch;
    }
    
    public void load(){
        try (BufferedReader rd = new BufferedReader(new FileReader(filePath))){
            String line;
            while ((line = rd.readLine()) != null){
            String[] pt = line.split(",");
                
                if(pt.length == 2){
                    String numTel = pt[0].trim();
                    String nom = pt[1].trim();
                    conts.put(numTel, nom);
                }
            }
            
            System.out.println("Datos del contacto exitosos.");
            
        } catch (Exception e) {
            System.out.println("Error al cargar datos de contactos:"+e.getMessage());            
        }
    }
    
    public void almacen(){
        try (BufferedWriter wr = new BufferedWriter(new FileWriter(filePath))){
            for (Map.Entry<String, String> entry:conts.entrySet()){
                String numTel = entry.getKey();
                String nom = entry.getValue();
                wr.write(numTel + "," + nom);
                wr.newLine();
            }
            System.out.println("Contacto almacenada exitosamente.");
        } catch (Exception e) {
            System.out.println("Erros de almacenamiento del contacto:" + e.getMessage());
        }
    }
    
    public void list(){
        System.out.println("Contactos.");
        for(Map.Entry<String, String> entry:conts.entrySet()){
            String numTel = entry.getKey();
            String nom = entry.getValue();
            System.out.println(numTel + "," + nom);
        }
    }
    
    public void crear(String numTel, String nom){
        conts.put(numTel, nom);
        System.out.println("Contacto creado correctamente.");
    }
    
    public void eliminar(String numTel){
        if(conts.containsKey(numTel)){
            conts.remove(numTel);
            System.out.println("Contacto eliminado correctamente.");
        }else{
            System.out.println("El contacto no existe.");
        }
    }
    
    public void menu(){
        Scanner sc = new Scanner(System.in);
        boolean salir = false;
        
        while(!salir){
            System.out.println("AdressBook.");
            System.out.println("1.- Contactos");
            System.out.println("2.- Almacenar contacto");
            System.out.println("3.- Eliminar contacto");
            System.out.println("4.- Almacenar cambios de contacto");
            System.out.println("5.- salir");
            System.out.println("");
            System.out.println("Elige opción deseada.");
            int op = sc.nextInt();
            sc.nextLine();
            
            switch(op){
                case 1:
                    list();
                    System.out.println("");
                    break;
                    
                case 2:
                    System.out.println("Favor de ingresar nombre de contacto:");
                    String nom =sc.nextLine();
                    System.out.println("Favor de ingresar número de contacto.");
                    String numTel =sc.nextLine();
                    crear(numTel, nom);
                    System.out.println("");
                    break;
                    
                case 3:
                    System.out.println("Ingresar núumero a eliminar");
                    String numElim = sc.nextLine();
                    eliminar(numElim);
                    System.out.println("");
                    break;
                case 4:
                    almacen();
                    System.out.println("");
                    break;
                case 5:
                    salir = true;
                    System.out.println("");
                    System.out.println("Geacias, su visita");
                    System.out.println("");
                    break;
                default:
                    System.out.println("Opcion no valida, favor de intenrtarlo de nuevo.");
                    
                    break;
        }
        }
        sc.close();
        }
    public static void main(String[] arg){
        adrressBook addBook = new adrressBook("conts.csv");
        addBook.load();
        addBook.menu();
    }
}
