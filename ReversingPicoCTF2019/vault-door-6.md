# vault-door-6

## Objetivos
This vault uses an XOR encryption scheme. The source code for this vault is here: [VaultDoor6.java](https://jupiter.challenges.picoctf.org/static/86e94cc555b2ca7375424c884ef581a6/VaultDoor6.java)


## Solución 
```bash
>>> myBytes = [0x3b, 0x65, 0x21, 0xa , 0x38, 0x0 , 0x36, 0x1d,
...             0xa , 0x3d, 0x61, 0x27, 0x11, 0x66, 0x27, 0xa ,
...             0x21, 0x1d, 0x61, 0x3b, 0xa , 0x2d, 0x65, 0x27,
...             0xa , 0x66, 0x36, 0x30, 0x67, 0x6c, 0x64, 0x6c]
>>> myBytes
[59, 101, 33, 10, 56, 0, 54, 29, 10, 61, 97, 39, 17, 102, 39, 10, 33, 29, 97, 59, 10, 45, 101, 39, 10, 102, 54, 48, 103, 108, 100, 108]
>>> flag = [i ^ 0x55 for i in myBytes]
>>> flag
[110, 48, 116, 95, 109, 85, 99, 72, 95, 104, 52, 114, 68, 51, 114, 95, 116, 72, 52, 110, 95, 120, 48, 114, 95, 51, 99, 101, 50, 57, 49, 57]
>>> flag =[ chr(i) for i in flag ]
>>> ''.join(flag)
'n0t_mUcH_h4rD3r_tH4n_x0r_3ce2919'
>>> 

```

## Solución 2
``` java
import java.util.*;
class VaultDoor6 {
public static void main(String args[]) {
VaultDoor6 vaultDoor = new VaultDoor6();
Scanner scanner = new Scanner(System.in);
//System.out.print("Enter vault password: ");
//String userInput = scanner.next();
//String input = userInput.substring("picoCTF{".length(),userInput.length()-1);
if (vaultDoor.checkPassword()) {
System.out.println("Access granted.");
} else {
System.out.println("Access denied!");
}
}
// Dr. Evil gave me a book called Applied Cryptography by Bruce Schneier,
// and I learned this really cool encryption system. This will be the
// strongest vault door in Dr. Evil's entire evil volcano compound for sure!
// Well, I didn't exactly read the *whole* book, but I'm sure there's
// nothing important in the last 750 pages.
//
// -Minion #3091
public boolean checkPassword() {
/**if (password.length() != 32) {
return false;
}
byte[] passBytes = password.getBytes();*/
byte[] flagbytes = new byte[32];
byte[] myBytes = {
0x3b, 0x65, 0x21, 0xa , 0x38, 0x0 , 0x36, 0x1d,
0xa , 0x3d, 0x61, 0x27, 0x11, 0x66, 0x27, 0xa ,
0x21, 0x1d, 0x61, 0x3b, 0xa , 0x2d, 0x65, 0x27,
0xa , 0x66, 0x36, 0x30, 0x67, 0x6c, 0x64, 0x6c,
};
for (int i=0; i<32; i++) {
/*if (((passBytes[i] ^ 0x55) - myBytes[i]) != 0) {
return false;
}*/
flagbytes[i] = (byte)(myBytes[i] ^ 0x55);
}

String flag = new String(flagbytes);
System.out.println(flag);
return true;
}

```

```shell
┌──(kali㉿kali)-[~/Downloads]
└─$ java VaultDoor6      
Picked up _JAVA_OPTIONS: -Dawt.useSystemAAFontSettings=on -Dswing.aatext=true
n0t_mUcH_h4rD3r_tH4n_x0r_3ce2919
Access granted.
                             

```

## Notas adicionales 
Analizando el codigo vemos que en la funcion checkpassword donde es la función que verifica que nuestra conraseña sea correcta, hay una serie de bytes, a estos bytes tendríamos que hacer un exort y convertirlos a caracter para desencriptar nuestra contraseña