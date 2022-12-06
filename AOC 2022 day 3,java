import java.io.IOException;
import java.nio.charset.StandardCharsets;
import java.nio.charset.Charset;
import java.nio.file.Files;
import java.nio.file.Paths;
import java.nio.file.Path;
import java.util.List;
/**
 * Write a description of class Day3 here.
 *
 * @author (your name)
 * @version (a version number or a date)
 */
public class Day3
{
    public static void main(String[] args) {
        Path filePath = Paths.get("data.txt");
        Charset charset = StandardCharsets.UTF_8;
        List<String> dataLines;
        try 
        {
            dataLines = Files.readAllLines(filePath, charset);
        } 
        catch (IOException ex) 
        {
            System.out.format("I/O error: %s%n", ex);
            return;
        }
        long start = System.nanoTime();
        int sum = 0;
        int temp=0;
        int lowerindex=0;
        int upperindex=0;
        for(int i=0; i<dataLines.size(); i++)
        {
            String c = dataLines.get(i); 
            String side1 = c.substring(0, c.length()/2);
            String side2 = c.substring(c.length()/2, c.length());
            System.out.println(side1);
            System.out.println(side2);
            String lower = "abcdefghijklmnopqrstuvwxyz";
            String upper = "ABCDEFGHIJKLMNOPQRSTUVWXYZ";
            for(int o=0; o<c.length()/2; o++)
            {
                for(int q=0; q<c.length()/2; q++)
                {
                    if(side1.substring(o, o+1).equals(side2.substring(q, q+1)))
                    {
                        temp=side2.indexOf(side2.substring(q,q+1));
                    }
                }
            }
            for(int a1=0; a1<26; a1++)
            {
                if(side2.substring(temp, temp+1).equals(lower.substring(a1, a1+1)))
                {
                    lowerindex = 1+ lower.indexOf(lower.substring(a1,a1+1));
                    sum = sum+lowerindex;
                }
            }
            for(int a1=0; a1<26; a1++)
            {
                if(side2.substring(temp, temp+1).equals(upper.substring(a1, a1+1)))
                {
                    upperindex = 27+ upper.indexOf(upper.substring(a1,a1+1));
                    sum = sum+upperindex;
                }
            }
            System.out.println(sum);
        }
        long end = System.nanoTime();
        long elapsedTime = end - start;
        System.out.format("Elapsed time: %dns%n", elapsedTime);
    }
}
