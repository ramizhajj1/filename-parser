```
import java.io.*;
import java.util.Scanner;

public class App {

        //read files
        public static String[] parseLineBySpaces(String line) {
            return line.split("\\s+");
        }
        public static void main (String[] args) throws Exception {
            System.out.println(System.getProperty("user.dir"));
            //Creating the File object
            File file = new File("ramiz/dnsmasq/src/ASUSDDWRT-dnsmasq.leases");
            //Creating a Scanner object
            Scanner sc = new Scanner(file);
            //StringBuffer to store the contents
            StringBuffer sb = new StringBuffer();
            //Appending each line to the buffer
            while(sc.hasNext()) {
                //output files
                String[] parts = parseLineBySpaces(sc.nextLine());
                for (String part : parts) {
                    String ipAddress = parts[2];
                    String deviceName = parts[3];
                    String newFormat = String.format("<a class=\"btn btn-primary\" href=\"https://%s:4200/\" target=\"_blank\">%s</a><br><br>", ipAddress, deviceName);

                    System.out.println(newFormat);
                }
            
```
