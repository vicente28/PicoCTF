# vault-door-training

## Objetivos
Your mission is to enter Dr. Evil's laboratory and retrieve the blueprints for his Doomsday Project. The laboratory is protected by a series of locked vault doors. Each door is controlled by a computer and requires a password to open. Unfortunately, our undercover agents have not been able to obtain the secret passwords for the vault doors, but one of our junior agents obtained the source code for each vault's computer! You will need to read the source code for each level to figure out what the password is for that vault door. As a warmup, we have created a replica vault in our training facility. The source code for the training vault is here: [VaultDoorTraining.java](https://jupiter.challenges.picoctf.org/static/03c960ddcc761e6f7d1722d8e6212db3/VaultDoorTraining.java)


## Solución 
```bash
┌──(kali㉿kali)-[~/Downloads]
└─$ cat VaultDoorTraining.java     
import java.util.*;

class VaultDoorTraining {
    public static void main(String args[]) {
        VaultDoorTraining vaultDoor = new VaultDoorTraining();
        Scanner scanner = new Scanner(System.in); 
        System.out.print("Enter vault password: ");
        String userInput = scanner.next();
        String input = userInput.substring("picoCTF{".length(),userInput.length()-1);
        if (vaultDoor.checkPassword(input)) {
            System.out.println("Access granted.");
        } else {
            System.out.println("Access denied!");
        }
   }

    // The password is below. Is it safe to put the password in the source code?
    // What if somebody stole our source code? Then they would know what our
    // password is. Hmm... I will think of some ways to improve the security
    // on the other doors.
    //
    // -Minion #9567
    public boolean checkPassword(String password) {
        return password.equals("w4rm1ng_Up_w1tH_jAv4_3808d338b46");
    }
}
┌──(kali㉿kali)-[~/Downloads]
└─$ javac VaultDoorTraining.java 
Picked up _JAVA_OPTIONS: -Dawt.useSystemAAFontSettings=on -Dswing.aatext=true
                                                                                                                   
┌──(kali㉿kali)-[~/Downloads]
└─$ ls
audacity-linux-3.2.1-x64.AppImage  Obsidian-1.0.0.AppImage  VaultDoorTraining.java
caxcan-club.py                     VaultDoorTraining.class
                                                                                                                   
┌──(kali㉿kali)-[~/Downloads]
└─$ java VaultDoorTraining    
Picked up _JAVA_OPTIONS: -Dawt.useSystemAAFontSettings=on -Dswing.aatext=true
Enter vault password: picoCTF{w4rm1ng_Up_w1tH_jAv4_3808d338b46}
Access granted.
                                                                                                                   
┌──(kali㉿kali)-[~/Downloads]
└─$ 

```

## Notas adicionales 

Para este reto es simple abrimos el codigo fuente y analizando el codigo notamos que para que valide la contraseña debe ser igual a un string que tenemos el obsevar el codigo fuente,
lo que tenemos que hacer es ponerlo en el formato de una bandera de pico 