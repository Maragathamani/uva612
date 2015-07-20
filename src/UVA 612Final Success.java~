import java.io.BufferedReader;
import java.io.IOException;
import java.io.InputStreamReader;
import java.util.*;

/**
 * Created with IntelliJ IDEA.
 * User: Maragathamani
 * Date: 2/8/14
 * Time: 11:42 PM
 * To change this template use File | Settings | File Templates.
 */
class TestMap {

    public static Integer n = 0;    // Length of strings.
    public static int M = 0;    // Number of data sets.
    public static Integer m = 0;    // Number of Strings.
    public static boolean blank = true;
//    public static HashMap<Integer, String> cache = new HashMap<Integer, String>();
//    public static Map<Integer, String> treeMap = new TreeMap<Integer, String>();

    public static void main(String[] args) {

        BufferedReader br = new BufferedReader(new InputStreamReader(System.in));
//        System.out.println("M: ");
        try {
            M = Integer.parseInt(br.readLine());
        } catch (IOException e) {
            e.printStackTrace();  //To change body of catch statement use File | Settings | File Templates.
        }

        while (M > 0) {
            Map<Integer, ArrayList<String>> treeMap = new TreeMap<Integer, ArrayList<String>>();
            try {

//                System.out.println();
                String blankLine = br.readLine();
                if (blankLine.equals("")) {

                }
                String num = br.readLine();
                String narr[] = num.trim().split(" ");
                n = Integer.parseInt(narr[0].trim());
                m = Integer.parseInt(narr[1].trim());
                String[] input = new String[m];
                int[] inputCount = new int[m];

                for (int i = 0; i < m; i++) {
                    input[i] = br.readLine();
                    ArrayList<String> input2 = new ArrayList<String>();
                    input2.add(input[i]);
                    inputCount[i] = count(input[i]);
                    if(treeMap.get(inputCount[i]) == null){
                    treeMap.put(inputCount[i], input2);
                    }
                    else{
                        ArrayList<String> temp = treeMap.get(inputCount[i]);
                        temp.add(input[i]);
                        treeMap.put(inputCount[i], temp);
                    }
                }

//                for (int j = 0; j < m; j++) {
//                    cache.put(inputCount[j], input[j]);
//                }

//                treeMap = new TreeMap<Integer, String>(cache);
            } catch (IOException e) {
                e.printStackTrace();  //To change body of catch statement use File | Settings | File Templates.
            } catch (ArrayIndexOutOfBoundsException e) {
                e.printStackTrace();
            } catch (NullPointerException e) {
                e.printStackTrace();
            } catch (NumberFormatException e) {
                e.printStackTrace();
            }
            printMap(treeMap);
            M--;
        }

    }

    /*
    This method will print the output
      as from Most sorted to least sorted.
     */
    public static void printMap(Map<Integer, ArrayList<String>> map) {
        if(!blank){
            System.out.println();
        }
        blank = false;
        for (Map.Entry<Integer, ArrayList<String>> entry : map.entrySet()) {
//            System.out.println("Key : " + entry.getKey() + " Value : "
//                    + entry.getValue());
//            String[] strings = (String[]) entry.getValue();
            ArrayList<String> temp = entry.getValue();
            for(String n : temp){
                System.out.println(n);
            }
//            for(String[] arr : entry.getValue()){
//            System.out.println(Arrays.toString(arr));
//            }

        }
       /* for(int i=0; i<map.size();i++){
            if(map.get(i)==null){

            }
            else{
                for(String n : map.get(i)){
                    System.out.println(n);
                }
            }
//            ArrayList<String> temp = map.get(i);
//            String[] strings = (String[]) map.get(i);
//            System.out.println(strings);
        } */
//        System.out.println("\n");
    }

    /*
    This method will calculates the "unsortedness" measure
    for each given string.
     */
    public static int count(String input) {
        int count = 0;
        for (int i = 0; i < n; i++) {
            if (charValue(input.charAt(i)) != 0) {
                for (int j = i + 1; j < n; j++) {
                    if (charValue(input.charAt(i)) > charValue(input.charAt(j))) {
                        count++;
                    }
                }
            }
        }
        return count;
    }

    /*
    This method assigns a value for each char (A, C, G, T).
     */
    public static Integer charValue(char x) {
        if (x == 'A')
            return 0;
        else if (x == 'C')
            return 1;
        else if (x == 'G')
            return 2;
        else if (x == 'T')
            return 3;
        return null;
    }
}