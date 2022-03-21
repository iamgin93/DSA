Write a program which removes specific characters from a string.
Each source string and characters you need to scrub are delimited by comma.

Input sample:

how are you, abc
hello world, def
Output sample:

how re you
hllo worl

public class Main{

    public static void main(String[] args) throws IOException {
        File file = new File(args[0]);
        BufferedReader br = new BufferedReader(new FileReader(file));           
            String s;
            while ((s = br.readLine()) != null) {
                s = s.trim();
                String arr[]=s.split(",\\s");
                String pat="([^"+arr[1]+"])";
                Pattern p=Pattern.compile(pat);
                Matcher m=p.matcher(arr[0]);
                while(m.find())
                {
                    System.out.print(m.group(0));
                }
                System.out.println();
            }
            br.close();
        }

    }
