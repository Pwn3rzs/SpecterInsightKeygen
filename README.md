### Specter Insight C2 Keygen

#### Setup

##### Certificate Generation for Keygen

 - Generate EDCSA Key
	- `openssl ecparam -name prime256v1 -genkey -noout -out cert.key`
 - Generate CSR File
	- `openssl req -new -key .\cert.key -out ecdsa_request.csr -subj "/C=RU/ST=Russia/L=Moscow/O=Pwn3rzs/OU=CyberArsenal/CN=Pwn3rzs 'nd CyberArsenal"`
 - Self Sign Certificate
   - `openssl x509 -req -in ecdsa_request.csr -signkey .\cert.key -out cert.pem -days 3650`
 - Export as P12 Certificate
	- `openssl pkcs12 -export -out cert.p12 -inkey .\cert.key -in .\cert.pem -name "SpecterInsight Keygen Cert"`
	- NOTE: For the keygen, you can password protect it, but for replacemente, it MUST be without password.

##### Replace Certificate in Server and Client

 -  With any software that lets you edit .NET Resource Files, replace the resource called "Validator" inside this two DLL:
	- `<base_path>/client/SpecterInsight.UI.dll`
	- `<base_path>/server/SpecterInsight.Server.dll`
 - Replace with your current non password protected P12 certificate and let it keep the name ""Validator"
 - Now you're ready to use the keygen.

##### Running the keygen

 - Execute "SpecterInsightKeygen.exe"
 - Follow the guidelines shown by the software.
	- In few words: just put the saved "license.json" file into `<base_path>/settings/` directory.
 - Enjoy!

#### Build
 
##### Requirements
 - .NET 8.0 LTS
 - WPF UI 
 - Visual Studio

##### Release / Debug build

 - Just load `SpecterInsightKeygen.sln` with Visual Studio
 - Choose `Debug` or `Release` and hit Build
 - Enjoy!