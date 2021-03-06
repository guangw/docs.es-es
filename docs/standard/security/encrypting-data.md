---
title: Cifrar datos
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- encryption [.NET Framework], symmetric
- symmetric encryption
- cryptography [.NET Framework], asymmetric
- asymmetric encryption
ms.assetid: 7ecce51f-db5f-4bd4-9321-cceb6fcb2a77
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 39dd7bfe4e5dd3405e24bf044723dbd92ccc65a3
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
---
# <a name="encrypting-data"></a>Cifrar datos
El cifrado simétrico y el cifrado asimétrico se efectúan mediante procesos distintos. El cifrado simétrico se realiza en secuencias y, por tanto, resulta útil para cifrar grandes cantidades de datos. El cifrado asimétrico se realiza en un pequeño número de bytes y, por tanto, solo resulta útil para pequeñas cantidades de datos.  
  
## <a name="symmetric-encryption"></a>Cifrado simétrico  
 Las clases de criptografía simétrica administrada se usan con una clase de secuencia especial llamada <xref:System.Security.Cryptography.CryptoStream> que cifra los datos leídos en la secuencia. La clase **CryptoStream** se inicializa con una clase de secuencia administrada, una clase que implementa la interfaz <xref:System.Security.Cryptography.ICryptoTransform> (creada a partir de una clase que implementa un algoritmo criptográfico) y una enumeración <xref:System.Security.Cryptography.CryptoStreamMode> que describe el tipo de acceso permitido a **CryptoStream**. La clase **CryptoStream** puede inicializarse usando cualquier clase que derive de la clase <xref:System.IO.Stream> , incluidas <xref:System.IO.FileStream>, <xref:System.IO.MemoryStream>y <xref:System.Net.Sockets.NetworkStream>. Mediante estas clases, puede realizar el cifrado simétrico en diversos objetos de secuencia.  
  
 En el ejemplo siguiente se muestra cómo crear una nueva instancia de la clase <xref:System.Security.Cryptography.RijndaelManaged> , que implementa el algoritmo de cifrado Rijndael, y usarla para realizar el cifrado en una clase **CryptoStream** . En este ejemplo, **CryptoStream** se inicializa con un objeto de secuencia llamado `MyStream` que puede ser cualquier tipo de secuencia administrada. Se pasan la clave y el IV que se usan para el cifrado al método **CreateEncryptor** de la clase **RijndaelManaged** . En este caso, se usan la clave predeterminada y el IV generados desde `RMCrypto` . Por último, se pasa **CryptoStreamMode.Write y** , que especifica el acceso de escritura a la secuencia.  
  
```vb  
Dim RMCrypto As New RijndaelManaged()  
Dim CryptStream As New CryptoStream(MyStream, RMCrypto.CreateEncryptor(RMCrypto.Key, RMCrypto.IV), CryptoStreamMode.Write)  
```  
  
```csharp  
RijndaelManaged RMCrypto = new RijndaelManaged();  
CryptoStream CryptStream = new CryptoStream(MyStream, RMCrypto.CreateEncryptor(), CryptoStreamMode.Write);  
```  
  
 Después de que se ejecute este código, los datos escritos en el objeto **CryptoStream** se cifran usando el algoritmo Rijndael.  
  
 En el ejemplo siguiente se muestra todo el proceso de crear una secuencia, cifrarla, escribir en ella y cerrarla. En este ejemplo se crea una secuencia de red que se cifra usando las clases **CryptoStream** y **RijndaelManaged** . Se escribe un mensaje en la secuencia cifrada con la clase <xref:System.IO.StreamWriter> .  
  
> [!NOTE]
>  También puede usar este ejemplo para escribir en un archivo. Para ello, elimine la referencia <xref:System.Net.Sockets.TcpClient> y reemplace <xref:System.Net.Sockets.NetworkStream> con <xref:System.IO.FileStream>.  
  
```vb  
Imports System  
Imports System.IO  
Imports System.Security.Cryptography  
Imports System.Net.Sockets  
  
Module Module1  
Sub Main()  
   Try  
      'Create a TCP connection to a listening TCP process.  
      'Use "localhost" to specify the current computer or  
      'replace "localhost" with the IP address of the   
      'listening process.   
      Dim TCP As New TcpClient("localhost", 11000)  
  
      'Create a network stream from the TCP connection.   
      Dim NetStream As NetworkStream = TCP.GetStream()  
  
      'Create a new instance of the RijndaelManaged class  
      'and encrypt the stream.  
      Dim RMCrypto As New RijndaelManaged()  
  
            Dim Key As Byte() = {&H1, &H2, &H3, &H4, &H5, &H6, &H7, &H8, &H9, &H10, &H11, &H12, &H13, &H14, &H15, &H16}  
            Dim IV As Byte() = {&H1, &H2, &H3, &H4, &H5, &H6, &H7, &H8, &H9, &H10, &H11, &H12, &H13, &H14, &H15, &H16}  
  
      'Create a CryptoStream, pass it the NetworkStream, and encrypt   
      'it with the Rijndael class.  
      Dim CryptStream As New CryptoStream(NetStream, RMCrypto.CreateEncryptor(Key, IV), CryptoStreamMode.Write)  
  
      'Create a StreamWriter for easy writing to the   
      'network stream.  
      Dim SWriter As New StreamWriter(CryptStream)  
  
      'Write to the stream.  
      SWriter.WriteLine("Hello World!")  
  
      'Inform the user that the message was written  
      'to the stream.  
      Console.WriteLine("The message was sent.")  
  
      'Close all the connections.  
      SWriter.Close()  
      CryptStream.Close()  
      NetStream.Close()  
      TCP.Close()  
   Catch  
      'Inform the user that an exception was raised.  
      Console.WriteLine("The connection failed.")  
   End Try  
End Sub  
End Module  
```  
  
```csharp  
using System;  
using System.IO;  
using System.Security.Cryptography;  
using System.Net.Sockets;  
  
public class main  
{  
   public static void Main(string[] args)  
   {  
      try  
      {  
         //Create a TCP connection to a listening TCP process.  
         //Use "localhost" to specify the current computer or  
         //replace "localhost" with the IP address of the   
         //listening process.    
         TcpClient TCP = new TcpClient("localhost",11000);  
  
         //Create a network stream from the TCP connection.   
         NetworkStream NetStream = TCP.GetStream();  
  
         //Create a new instance of the RijndaelManaged class  
         // and encrypt the stream.  
         RijndaelManaged RMCrypto = new RijndaelManaged();  
  
         byte[] Key = {0x01, 0x02, 0x03, 0x04, 0x05, 0x06, 0x07, 0x08, 0x09, 0x10, 0x11, 0x12, 0x13, 0x14, 0x15, 0x16};  
         byte[] IV = {0x01, 0x02, 0x03, 0x04, 0x05, 0x06, 0x07, 0x08, 0x09, 0x10, 0x11, 0x12, 0x13, 0x14, 0x15, 0x16};  
  
         //Create a CryptoStream, pass it the NetworkStream, and encrypt   
         //it with the Rijndael class.  
         CryptoStream CryptStream = new CryptoStream(NetStream,   
         RMCrypto.CreateEncryptor(Key, IV),     
         CryptoStreamMode.Write);  
  
         //Create a StreamWriter for easy writing to the   
         //network stream.  
         StreamWriter SWriter = new StreamWriter(CryptStream);  
  
         //Write to the stream.  
         SWriter.WriteLine("Hello World!");  
  
         //Inform the user that the message was written  
         //to the stream.  
         Console.WriteLine("The message was sent.");  
  
         //Close all the connections.  
         SWriter.Close();  
         CryptStream.Close();  
         NetStream.Close();  
         TCP.Close();  
      }  
      catch  
      {  
         //Inform the user that an exception was raised.  
         Console.WriteLine("The connection failed.");  
      }  
   }  
}  
```  
  
 Para que el ejemplo anterior se ejecute correctamente, debe haber un proceso escuchando en la dirección IP y un número de puerto especificado en la clase <xref:System.Net.Sockets.TcpClient> . Si existe un proceso de escucha, el código se conectará con el proceso de escucha, cifrará la secuencia usando el algoritmo simétrico Rijndael y escribirá "Hello World!" en la secuencia. Si el código es correcto, mostrará el texto siguiente en la consola:  
  
```  
The message was sent.  
```  
  
 Sin embargo, si no se encuentra ningún proceso de escucha o si se produce una excepción, el código muestra el texto siguiente en la consola:  
  
```  
The connection failed.  
```  
  
## <a name="asymmetric-encryption"></a>Cifrado asimétrico  
 Los algoritmos asimétricos suelen usarse para cifrar pequeñas cantidades de datos, como el cifrado de una clave simétrica y un IV. Normalmente, cuando se realiza un cifrado asimétrico, se usa la clave pública generada por terceros. .NET Framework proporciona la clase <xref:System.Security.Cryptography.RSACryptoServiceProvider> necesaria para este propósito.  
  
 En el ejemplo siguiente se usa la información de clave pública para cifrar una clave simétrica y un IV. Se inicializan dos matrices de bytes que representan la clave pública de un tercero. Se inicializa un objeto <xref:System.Security.Cryptography.RSAParameters> en estos valores. Después, el **RSAParameters** objeto (junto con la clave pública que representa) se importa a una **RSACryptoServiceProvider** mediante el <xref:System.Security.Cryptography.RSACryptoServiceProvider.ImportParameters%2A?displayProperty=nameWithType> método. Por último, se cifran la clave privada y el IV creados por una clase <xref:System.Security.Cryptography.RijndaelManaged> . Este ejemplo requiere sistemas que tengan instalado el cifrado de 128 bits.  
  
```vb  
Imports System  
Imports System.Security.Cryptography  
  
Module Module1  
  
    Sub Main()  
        'Initialize the byte arrays to the public key information.  
      Dim PublicKey As Byte() =  {214, 46, 220, 83, 160, 73, 40, 39, 201, 155, 19,202, 3, 11, 191, 178, 56, 74, 90, 36, 248, 103, 18, 144, 170, 163, 145, 87, 54, 61, 34, 220, 222, 207, 137, 149, 173, 14, 92, 120, 206, 222, 158, 28, 40, 24, 30, 16, 175, 108, 128, 35, 230, 118, 40, 121, 113, 125, 216, 130, 11, 24, 90, 48, 194, 240, 105, 44, 76, 34, 57, 249, 228, 125, 80, 38, 9, 136, 29, 117, 207, 139, 168, 181, 85, 137, 126, 10, 126, 242, 120, 247, 121, 8, 100, 12, 201, 171, 38, 226, 193, 180, 190, 117, 177, 87, 143, 242, 213, 11, 44, 180, 113, 93, 106, 99, 179, 68, 175, 211, 164, 116, 64, 148, 226, 254, 172, 147}  
  
        Dim Exponent As Byte() = {1, 0, 1}  
  
        'Create values to store encrypted symmetric keys.  
        Dim EncryptedSymmetricKey() As Byte  
        Dim EncryptedSymmetricIV() As Byte  
  
        'Create a new instance of the RSACryptoServiceProvider class.  
        Dim RSA As New RSACryptoServiceProvider()  
  
        'Create a new instance of the RSAParameters structure.  
        Dim RSAKeyInfo As New RSAParameters()  
  
        'Set RSAKeyInfo to the public key values.   
        RSAKeyInfo.Modulus = PublicKey  
        RSAKeyInfo.Exponent = Exponent  
  
        'Import key parameters into RSA.  
        RSA.ImportParameters(RSAKeyInfo)  
  
        'Create a new instance of the RijndaelManaged class.  
        Dim RM As New RijndaelManaged()  
  
        'Encrypt the symmetric key and IV.  
        EncryptedSymmetricKey = RSA.Encrypt(RM.Key, False)  
        EncryptedSymmetricIV = RSA.Encrypt(RM.IV, False)  
    End Sub  
  
End Module  
```  
  
```csharp  
using System;  
using System.Security.Cryptography;  
  
class Class1  
{  
   static void Main()  
   {  
      //Initialize the byte arrays to the public key information.  
      byte[] PublicKey = {214,46,220,83,160,73,40,39,201,155,19,202,3,11,191,178,56,  
            74,90,36,248,103,18,144,170,163,145,87,54,61,34,220,222,  
            207,137,149,173,14,92,120,206,222,158,28,40,24,30,16,175,  
            108,128,35,230,118,40,121,113,125,216,130,11,24,90,48,194,  
            240,105,44,76,34,57,249,228,125,80,38,9,136,29,117,207,139,  
            168,181,85,137,126,10,126,242,120,247,121,8,100,12,201,171,  
            38,226,193,180,190,117,177,87,143,242,213,11,44,180,113,93,  
            106,99,179,68,175,211,164,116,64,148,226,254,172,147};  
  
      byte[] Exponent = {1,0,1};  
  
      //Create values to store encrypted symmetric keys.  
      byte[] EncryptedSymmetricKey;  
      byte[] EncryptedSymmetricIV;  
  
      //Create a new instance of the RSACryptoServiceProvider class.  
      RSACryptoServiceProvider RSA = new RSACryptoServiceProvider();  
  
      //Create a new instance of the RSAParameters structure.  
      RSAParameters RSAKeyInfo = new RSAParameters();  
  
      //Set RSAKeyInfo to the public key values.   
      RSAKeyInfo.Modulus = PublicKey;  
      RSAKeyInfo.Exponent = Exponent;  
  
      //Import key parameters into RSA.  
      RSA.ImportParameters(RSAKeyInfo);  
  
      //Create a new instance of the RijndaelManaged class.  
      RijndaelManaged RM = new RijndaelManaged();  
  
      //Encrypt the symmetric key and IV.  
      EncryptedSymmetricKey = RSA.Encrypt(RM.Key, false);  
      EncryptedSymmetricIV = RSA.Encrypt(RM.IV, false);  
   }  
}  
```  
  
## <a name="see-also"></a>Vea también  
 [Generar claves para cifrado y descifrado](../../../docs/standard/security/generating-keys-for-encryption-and-decryption.md)  
 [Descifrar datos](../../../docs/standard/security/decrypting-data.md)  
 [Cryptographic Services](../../../docs/standard/security/cryptographic-services.md)
