---
title: Gerenciar as configurações de um console do Skype Room Systems v2 remotamente usando um arquivo de configuração XML
ms.author: jambirk
author: jambirk
ms.reviewer: davgroom
manager: serdars
ms.date: 1/31/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: df418e25-81fd-474d-be16-5cd1ac8145cc
description: Este artigo discute o gerenciamento remoto das configurações padrão usada por um dispositivo de v2 Skype sistemas de sala, incluindo a aplicação de um tema personalizado.
ms.openlocfilehash: 55a2dc3de11c4fbe8540740a52fe29a377264545
ms.sourcegitcommit: b265545216ff36772d5dc2df381a9046bc71098e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/13/2018
ms.locfileid: "23965972"
---
# <a name="manage-a-skype-room-systems-v2-console-settings-remotely-with-an-xml-configuration-file"></a>Gerenciar as configurações de um console do Skype Room Systems v2 remotamente usando um arquivo de configuração XML
 
Este artigo discute o gerenciamento remoto das configurações padrão usada por um dispositivo de v2 Skype sistemas de sala, incluindo a aplicação de um tema personalizado.
  
A atualização de um arquivo mestre XML e o envio de cópias aos consoles que você gerencia torna possível alterar as configurações padrão de dispositivos gerenciados remotamente. Este artigo aborda como criar esse arquivo e apresenta links para discussões de como colocá-lo conforme necessário nos dispositivos gerenciados remotamente. Usar esse método, você também pode implementar temas personalizados na suas consoles de v2 Skype sistemas de sala. 
  
## <a name="creating-an-xml-configuration-file"></a>Criando um arquivo de configuração XML

A tabela a seguir explica os elementos mostrados neste exemplo SkypeSettings.xml (isto é um nome de arquivo necessários) o arquivo de configuração. 
  
```
<SkypeSettings>
  <AutoScreenShare>true</AutoScreenShare>
  <HideMeetingName>true</HideMeetingName>
  <UserAccount>
             <SkypeSignInAddress>RanierConf@contoso.com</SkypeSignInAddress>
             <ExchangeAddress>RanierConf@contoso.com</ExchangeAddress>
             <DomainUsername>Seattle\RanierConf</DomainUsername>
             <Password>password</Password>
             <ConfigureDomain>domain1, domain2</ConfigureDomain>
  </UserAccount>    
  <IsTeamsDefaultClient>false</IsTeamsDefaultClient>
  <BluetoothAdvertisementEnabled>true</BluetoothAdvertisementEnabled>
  <SkypeMeetingsEnabled>false</SkypeMeetingsEnabled> 
  <TeamsMeetingsEnabled>true</TeamsMeetingsEnabled> 
  <DualScreenMode>true</DualScreenMode>
  <SendLogs>                           
             <EmailAddressForLogsAndFeedback>RanierConf@contoso.com</EmailAddressForLogsAndFeedback>
                <SendLogsAndFeedback>true</SendLogsAndFeedback>
  </SendLogs>
  <Devices>
              <MicrophoneForCommunication>Microsoft LifeChat LX-6000</MicrophoneForCommunication>
              <SpeakerForCommunication>Realtek High Definition Audio</SpeakerForCommunication>
              <DefaultSpeaker>Polycom CX5100</DefaultSpeaker>
  </Devices>
  <Theming> 
    <ThemeName>Custom</ThemeName>
       <CustomThemeImageUrl>folder path</CustomThemeImageUrl>
      <CustomThemeColor>
           <RedComponent>100</RedComponent>
           <GreenComponent>100</GreenComponent>
           <BlueComponent>100</BlueComponent>
         </CustomThemeColor>
  </Theming>
</SkypeSettings>
```

Se o arquivo XML formado incorretamente (ou seja, um valor da variável é do tipo incorreto, elementos fora de ordem, elementos são não fechados, e assim por diante), são aplicadas a configurações encontradas até o ponto onde o erro for encontrado e o restante do arquivo será ignorado durante o processamento. Quaisquer elementos desconhecidos no XML são ignorados. Se um parâmetro for omitido, ele não seja alterado no dispositivo. Se o valor de um parâmetro for inválido, o valor anterior permanecerá inalterado.
  
**Elementos XML**
 
|Elemento|Tipo|Nível|Uso|
|:--- |:--- |:--- |:--- |
|\<SkypeSettings\>   |Contêiner para todos os elementos.   ||Obrigatório.   |
| \<AutoScreenShare\>  |Boolean & #x 2777;  |Primeira & #x 2776;  | Se verdadeiro, o compartilhamento automático de tela será habilitado.  |
|\<HideMeetingName\>   |Boolean & #x 2777;  |Primeira & #x 2776;  |Se verdadeiro, os nomes das reuniões ficarão ocultos.   |
|\<UserAccount\>   |Contêiner   |Primeira & #x 2776;  |Contêiner para os parâmetros de credenciais.   Endereço, o endereço do Exchange ou o endereço de email de entrada geralmente é os mesmos, como RanierConf<span></span>@contoso.com.   |
|\<SkypeMeetingsEnabled\>  |Boolean & #x 2777;  |Primeira & #x 2776;  |Habilitado por padrão.   |
|\<SkypeSignInAddress\>   |Cadeia de caracteres & #x 2778;  ||O nome de entrada da conta do dispositivo do Skype for Business no console.   |
|\<ExchangeAddress\>   |Cadeia de caracteres & #x 2778;  ||O nome de entrada da conta do dispositivo do Exchange no console.   Se ExchangeAddress for omitido, SkypeSignInAddress não será reutilizado automaticamente.    |
|\<DomainUsername\>   |Cadeia de caracteres & #x 2778;  ||O domínio e o nome do usuário do dispositivo de console, por exemplo, Seattle\RanierConf.   |
|\<Senha\>   |Cadeia de caracteres 3  || O parâmetro de senha é a mesma senha usada para entrar na conta do dispositivo do Skype for Business.   |
| \<ConfigureDomain\>  |Cadeia de caracteres & #x 2778;  ||Você pode listar vários domínios, separados por vírgulas.   |
|\<TeamsMeetingsEnabled\>   |Boolean & #x 2777;  |Primeira & #x 2776;  |Desabilitado por padrão. <br/> <br/> O arquivo XML é considerado mal formado se ambos os \<SkypeMeetingsEnabled\> e\<TeamsMeetingsEnabled\> são desabilitadas, mas é aceitável ter ambas as configurações habilitadas ao mesmo tempo.   |
|\<IsTeamsDefaultClient > |Boolean & #x 2777;  |Primeira & #x 2776;  |Desabilitado por padrão. |
|\<BluetoothAdvertisementEnabled > |Boolean & #x 2777;  |Primeira & #x 2776;  |Habilitado por padrão. |
|\<DualScreenMode\>  |Boolean & #x 2777;  |Primeira & #x 2776;  |Se for true, o modo de tela dual está habilitado. Caso contrário, o dispositivo usará o modo de tela única.   |
|\<SendLogs\>   |Contêiner   |Primeira & #x 2776;  ||
|\<EmailAddressForLogsAndFeedback\>   |Cadeia de caracteres & #x 2778;  ||Define um endereço de email opcional para o qual os logs podem ser enviados quando a janela "Enviar Comentários" for exibida.    |
|\<SendLogsAndFeedback\>   |Boolean & #x 2777;  || Se verdadeiro, os logs são enviados para o administrador. Se falso, somente os comentários são enviados para o administrador (e não os logs).  |
| \<Dispositivos\>  |Contêiner   |Primeira & #x 2776;  | Os nomes dos dispositivos de áudio conectados nos elementos filho têm os mesmos valores listados no aplicativo Gerenciador de Dispositivos. A configuração pode conter um dispositivo que atualmente não existe no sistema, como um dispositivo de A/V que não está conectado ao console. A configuração seria mantida para o dispositivo correspondente.  |
|\<MicrophoneForCommunication\>   |Cadeia de caracteres & #x 2778;  ||Define o microfone que será usado como dispositivo de gravação em uma conferência.   |
|\<SpeakerForCommunication\>   |Cadeia de caracteres & #x 2778;  ||Dispositivo que deve ser usado como alto-falante para a conferência. Essa configuração é usada para definir o dispositivo alto-falante que será usado para ouvir o áudio de uma chamada.   |
|\<DefaultSpeaker\>   |Cadeia de caracteres & #x 2778;  ||Dispositivo que deve ser usado para executar o áudio de uma fonte de ingestão HDMI.    |
| \<Temas\>  |Contêiner   |Primeira & #x 2776;  |Um dos recursos que podem ser aplicados usando um arquivo XML é um tema personalizado para a sua organização. Você poderá especificar um nome do tema, imagem de plano de fundo e cores.   |
|\<ThemeName\>   |Cadeia de caracteres & #x 2778;  || Usado para identificar o tema no cliente. As opções de Nome do Tema são Padrão, um dos temas predefinidos fornecidos ou Personalizado. <br/>  Nomes de tema personalizado sempre devem usar o nome *personalizado* . A interface do usuário do cliente pode ser definida no console como Padrão ou um dos predefinidos, mas a aplicação de um tema personalizado deve ser definida remotamente por um administrador. <br/>  Os temas predefinidos incluem:  <br/>  Padrão <br/>  Onda Azul <br/>  Floresta Digital <br/>  Apanhador de Sonhos <br/>  Suco de Lima <br/>  Pixel Perfeito <br/>  Mapa Rodoviário <br/>  Pôr do Sol <br/>  Para desabilitar o tema atual, use "Sem tema" para o ThemeName.  |
|\<CustomThemeImageUrl\>   |Cadeia de caracteres & #x 2778;  ||Necessário se estiver usando um tema personalizado, caso contrário, é opcional. Consulte a seção de [Imagens personalizadas do tema](xml-config-file.md#Themes) abaixo para obter mais detalhes sobre a imagem de tema personalizado.  |
|\<CustomThemeColor\>   |Contêiner   ||Contêiner para o \<RedComponent\>, \<GreenComponent\>, e \<BlueComponent\> valores. Esses valores são obrigatórios ao usar um tema personalizado.   |
|\<RedComponent\>   |Byte (0-255)   ||Representa o componente da cor vermelha.   |
|\<GreenComponent\>   |Byte (0-255)   ||Representa o componente da cor verde.   |
|\<BlueComponent\>   |Byte (0-255)   ||Representa o componente da cor azul.   |
| | | |
   
& #x 2776; Todos os elementos de primeiro nível são opcionais. Se um elemento de primeiro nível for omitido, todos os seus parâmetros filho permanecerão inalterados no dispositivo.
  
& #x 2777; Um sinalizador booleano pode ser qualquer um dos seguintes: true, false, 0 ou 1. Os valores boolianos ou numéricos deixados vazios podem fazer com que o XML fique defeituoso, então as configurações não seriam alteradas.
  
 & #x 2778; Se um parâmetro de cadeia de caracteres for apresentar, Esvaziar e vazio é um valor válido, o parâmetro está desmarcado no dispositivo.
  
## <a name="manage-console-settings-using-an-xml-configuration-file"></a>Gerenciar as configurações do console usando um arquivo de configuração XML

Na inicialização, se um console do Skype sala sistemas v2 encontra um arquivo XML denominado SkypeSettings.xml no local **C:\Users\Skype\AppData\Local\Packages\Microsoft.SkypeRoomSystem_8wekyb3d8bbwe\LocalState**, ele aplicará as definições de configuração indicado pelo arquivo XML, então, excluir o arquivo XML.
  
Quantos dispositivos v2 de sistemas de sala Skype dependendo da sua empresa tenha e como você optar por gerenciar configurá-los, há várias maneiras de colocar o arquivo de configuração XML. Quando o arquivo for enviado por push para o console, reinicie-o para processar as alterações de configuração. O arquivo de configuração XML é excluído após seu processamento bem-sucedido. Os métodos de gerenciamento sugeridos para dispositivos do Skype sala sistemas v2 são abordados em:
  
- [Configurando a Política de Grupo para o Skype Room Systems v2](room-systems-v2-operations.md#GroupPolicy)
    
- [Gerenciamento remoto usando o PowerShell](room-systems-v2-operations.md#RemotePS) e [Configure um Item de arquivo](https://technet.microsoft.com/library/cc772536%28v=ws.11%29.aspx)
    
Você pode usar o método de sua preferência, desde que possa usá-lo para transferir arquivos e disparar a reinicialização do dispositivo de console. O arquivo deve ser capaz de excluir pela conta de usuário local do dispositivo (preferencialmente, ele deve pertencer a e têm privilégios totais concedido a esse usuário), gravável e legíveis. Se as permissões do arquivo não forem definidas corretamente, o software pode não conseguir aplicar as configurações, pode não conseguir excluir o arquivo após o processamento bem-sucedido e, possivelmente, pode até falhar.
  
## <a name="custom-theme-images"></a>Imagens de tema personalizado
<a name="Themes"> </a>

O arquivo de imagem de tema personalizado deve ser colocado no **C:\Users\Skype\AppData\Local\Packages\Microsoft.SkypeRoomSystem_8wekyb3d8bbwe\LocalState**, digite apenas o nome de arquivo e extensão no \<CustomThemeImageUrl\> variável.
  
O arquivo de imagem deve ter exatamente 3840X1080 pixels e estar em um destes formatos: jpg, jpeg, png e bmp. Se sua organização deseja uma imagem personalizada, um designer gráfico será útil nosso [Modelo de Photoshop tema personalizado](https://go.microsoft.com/fwlink/?linkid=870441) . Ele contém mais detalhes sobre onde colocar vários elementos em uma imagem do tema e as áreas que aparecerão na consoles e a exibe.
  
O arquivo de configuração XML deve ser atualizado na inicialização do dispositivo para reconhecer a imagem de tema. Depois que o novo arquivo XML for processado e excluído, o arquivo gráfico do tema será excluído do diretório.
  
## <a name="see-also"></a>Consulte também


[Gerenciar o Skype Room Systems versão 2](skype-room-systems-v2.md)

[Configurar um Item de arquivo](https://technet.microsoft.com/library/cc772536%28v=ws.11%29.aspx)
