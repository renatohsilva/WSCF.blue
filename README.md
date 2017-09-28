# WSCF.blue

forked from https://wscfblue.codeplex.com/ (it will be shut down soon)

```
- Stubs gerados a partir do WSCF.blue (só para Visual Studio 2013. Está deprecated a adição de plugins no 2015)
https://wscfblue.codeplex.com/

Instalação
Baixar e instalar.
Seguir os passos abaixo
1) Go to "C:\Program Files (x86)\thinktecture\WSCF.blue"
2) Copy "WSCF.blue.VS2010.addin" and rename the copy to "WSCF.blue.VS2013.addin"
3) Open "WSCF.blue.VS2013.addin" with a text editor (eg Notepad++)
4) Change the host application's version number from 10.0 to 12.0 as follows:
<HostApplication>
     <Name>Microsoft Visual Studio</Name>
     <Version>12.0</Version>
   </HostApplication>
5) If the path "C:\Program Files (x86)\thinktecture\WSCF.blue\" is not added in Visual Studio 2013 addin file-paths list, go in Visual Studio 2013's menu: Tools->Options->Environment->Add-in Security and then add the path
6) Restart the Visual Studio 2013 IDE

Parâmetros para geração

- Service/Client (gerar para os dois)
  -> Generate Web Service Code
  -> Service Side Stub
  Options
   - Separate Files
   - List<T>
   Service Behavior
   - Single
   - PerCall
   - Use Synchronization Context
   Service Method Implementation
   - Generate a regular service class with methods that throw a NotImplementedException in their body
   
   Destination namespace -> importante definir o namespace de acordo com o negócio. 

   - Remember Settings
   - Overwrite existing files


   IMPORTANTE

   Nas interfaces *PortType, na annotation "OperationContractAttribute", deixar Action com o valor "*"

   Exemplo:
   [System.ServiceModel.OperationContractAttribute(Action = "*", ReplyAction = "")]

   Isso deve ser feito de forma manual, após gerar os stubs. Causa não seja feito, o WSD da Unimed (Java) apresenta erro ao invocar o serviço
   
   ```

