/******************************************************************************

                            Online Java Compiler.
                Code, Compile, Run and Debug java program online.
Write your code in this editor and press "Run" button to execute it.

*******************************************************************************/
import java.util.Scanner;
class Encryption
{
    public String msgencryption(String msg,int key)
    {
        String encrypt="";
       int v=(key%65510);
	  
        for(int i=0;i<msg.length();i++)
        {
            char z=msg.charAt(i);
	      int g=z+v;
	      char f=(char)g;
	      encrypt+=Character.toString(f);
        }
        System.out.println(encrypt);
        return encrypt;
    }
}

class Decryption
{
    public String msgdecryption(String encryptedmsg)
    {
         int key;
         String decrypt="";
        System.out.println("enter the key to decrypt");
        Scanner a=new Scanner(System.in);
        {
            key=a.nextInt();
        }
        key=key%65510;
        for(int i=0;i<encryptedmsg.length();i++)
        {
              char z=encryptedmsg.charAt(i);
	          int g=z-key;
	       char f=(char)g;
	       decrypt+=Character.toString(f);
        }
        
        return decrypt;
    }
}
public class Main
{
	public static void main(String[] args) {
	    String msg="";
	    int n;
	    System.out.println("enter the message here");
	    Scanner s=new Scanner(System.in);
	    {
	       msg=s.nextLine();   
	       System.out.println("enter the key here");
	       n=s.nextInt();
	    }
	    
	    Encryption e=new Encryption();
	   String enc=e.msgencryption(msg,n);
	  
	  Decryption d=new Decryption();
	    System.out.println(d.msgdecryption(enc));
	
	
	}
}

