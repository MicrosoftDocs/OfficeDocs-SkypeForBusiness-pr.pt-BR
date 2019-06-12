---
title: Gerenciar as configurações de um console de salas do Microsoft Teams remotamente com um arquivo de configuração XML
ms.author: v-lanac
author: lanachin
ms.reviewer: davgroom
manager: serdars
ms.date: 1/31/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: df418e25-81fd-474d-be16-5cd1ac8145cc
ms.collection: M365-voice
description: Este artigo discute o gerenciamento remoto das configurações padrão usadas por um dispositivo de salas do Microsoft Teams, incluindo a aplicação de um tema personalizado.
ms.openlocfilehash: 998702a7af98b72139b7f4f20916937ebf7fc247
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34305329"
---
# <a name="manage-a-microsoft-teams-rooms-console-settings-remotely-with-an-xml-configuration-file"></a>Gerenciar as configurações de um console de salas do Microsoft Teams remotamente com um arquivo de configuração XML
 
Este artigo discute o gerenciamento remoto das configurações padrão usadas por um dispositivo de salas do Microsoft Teams, incluindo a aplicação de um tema personalizado.
  
A atualização de um arquivo mestre XML e o envio de cópias aos consoles que você gerencia torna possível alterar as configurações padrão de dispositivos gerenciados remotamente. Este artigo aborda como criar esse arquivo e apresenta links para discussões de como colocá-lo conforme necessário nos dispositivos gerenciados remotamente. Usando esse método, você também pode implementar temas personalizados em seus consoles de sala do Microsoft Teams. 
  
## <a name="creating-an-xml-configuration-file"></a>Criando um arquivo de configuração XML

A tabela a seguir explica os elementos mostrados neste arquivo de configuração de exemplo SkypeSettings. XML (esse é um nome de arquivo obrigatório). 
  
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

Se o arquivo XML estiver mal formado (ou seja, um valor de variável for do tipo errado, os elementos estiverem fora da ordem, os elementos não forem fechados e assim por diante), as configurações encontradas até o ponto em que o erro foi encontrado serão aplicadas, e o restante do arquivo será ignorado durante o processamento. Todos os elementos desconhecidos do XML serão ignorados. Se um parâmetro for omitido, ele permanecerá inalterado no dispositivo. Se o valor de um parâmetro for inválido, seu valor anterior permanecerá inalterado.
  
**Elementos XML**
 
|Elemento|Tipo|Nível|Uso|
|:--- |:--- |:--- |:--- |
|\<SkypeSettings\>   |Contêiner para todos os elementos.   ||Obrigatório.   |
| \<AutoScreenShare\>  |&#x2777; Boolean  |Primeiro &#x2776;  | Se verdadeiro, o compartilhamento automático de tela será habilitado.  |
|\<HideMeetingName\>   |&#x2777; Boolean  |Primeiro &#x2776;  |Se verdadeiro, os nomes das reuniões ficarão ocultos.   |
|\<UserAccount\>   |Contêiner   |Primeiro &#x2776;  |Contêiner para os parâmetros de credenciais.   O endereço de entrada, endereço do Exchange ou endereço de email geralmente é o mesmo, como RanierConf<span></span>@contoso. com.   |
|\<SkypeMeetingsEnabled\>  |&#x2777; Boolean  |Primeiro &#x2776;  |Habilitado por padrão.   |
|\<SkypeSignInAddress\>   |Cadeia de caracteres &#x2778;  ||O nome de entrada da conta do dispositivo do Skype for Business no console.   |
|\<ExchangeAddress\>   |Cadeia de caracteres &#x2778;  ||O nome de entrada da conta do dispositivo do Exchange no console.   Se ExchangeAddress for omitido, SkypeSignInAddress não será reutilizado automaticamente.    |
|\<DomainUsername\>   |Cadeia de caracteres &#x2778;  ||O domínio e o nome do usuário do dispositivo de console, por exemplo, Seattle\RanierConf.   |
|\<Passe\>   |Cadeia de caracteres 3  || O parâmetro de senha é a mesma senha usada para entrar na conta do dispositivo do Skype for Business.   |
| \<ConfigureDomain\>  |Cadeia de caracteres &#x2778;  ||Você pode listar vários domínios, separados por vírgulas.   |
|\<TeamsMeetingsEnabled\>   |&#x2777; Boolean  |Primeiro &#x2776;  |Desabilitado por padrão. <br/> <br/> O arquivo XML é considerado mal formado se ambos \<os\> SkypeMeetingsEnabled\<e\> TeamsMeetingsEnabled estiverem desativados, mas é aceitável ter ambas as configurações habilitadas ao mesmo tempo.   |
|\<IsTeamsDefaultClient> |&#x2777; Boolean  |Primeiro &#x2776;  |Desabilitado por padrão. |
|\<BluetoothAdvertisementEnabled> |&#x2777; Boolean  |Primeiro &#x2776;  |Habilitado por padrão. |
|\<DualScreenMode\>  |&#x2777; Boolean  |Primeiro &#x2776;  |Se verdadeiro, o modo de tela dupla está habilitado. Caso contrário, o dispositivo usará o modo de tela única.   |
|\<SendLogs\>   |Contêiner   |Primeiro &#x2776;  ||
|\<EmailAddressForLogsAndFeedback\>   |Cadeia de caracteres &#x2778;  ||Define um endereço de email opcional para o qual os logs podem ser enviados quando a janela "Enviar Comentários" for exibida.    |
|\<SendLogsAndFeedback\>   |&#x2777; Boolean  || Se verdadeiro, os logs são enviados para o administrador. Se falso, somente os comentários são enviados para o administrador (e não os logs).  |
| \<Dispositivos\>  |Contêiner   |Primeiro &#x2776;  | Os nomes dos dispositivos de áudio conectados nos elementos filho têm os mesmos valores listados no aplicativo Gerenciador de Dispositivos. A configuração pode conter um dispositivo que atualmente não existe no sistema, como um dispositivo de A/V que não está conectado ao console. A configuração seria mantida para o dispositivo correspondente.  |
|\<MicrophoneForCommunication\>   |Cadeia de caracteres &#x2778;  ||Define o microfone que será usado como dispositivo de gravação em uma conferência.   |
|\<SpeakerForCommunication\>   |Cadeia de caracteres &#x2778;  ||Dispositivo que deve ser usado como alto-falante para a conferência. Essa configuração é usada para definir o dispositivo alto-falante que será usado para ouvir o áudio de uma chamada.   |
|\<Defaultspeakr\>   |Cadeia de caracteres &#x2778;  ||Dispositivo que deve ser usado para executar o áudio de uma fonte de ingestão HDMI.    |
| \<Temas\>  |Contêiner   |Primeiro &#x2776;  |Um dos recursos que podem ser aplicados usando um arquivo XML é um tema personalizado para a sua organização. Você poderá especificar um nome de tema, uma imagem de plano de fundo e uma cor.   |
|\<ThemeName\>   |Cadeia de caracteres &#x2778;  || Usado para identificar o tema no cliente. As opções de Nome do Tema são Padrão, um dos temas predefinidos fornecidos ou Personalizado. <br/>  Os nomes de temas personalizados sempre devem usar o nome *personalizado* . A interface do usuário do cliente pode ser definida no console como Padrão ou um dos predefinidos, mas a aplicação de um tema personalizado deve ser definida remotamente por um administrador. <br/>  Os temas predefinidos incluem:  <br/>  Padrão <br/>  Onda Azul <br/>  Floresta Digital <br/>  Apanhador de Sonhos <br/>  Suco de Lima <br/>  Pixel Perfeito <br/>  Mapa Rodoviário <br/>  Pôr do Sol <br/>  Para desabilitar o tema atual, use "nenhum tema" para o ThemeName.  |
|\<CustomThemeImageUrl\>   |Cadeia de caracteres &#x2778;  ||É obrigatória quando se usa um tema personalizado, caso contrário, opcional. Consulte a seção [imagens de tema personalizadas](xml-config-file.md#Themes) abaixo para obter mais detalhes sobre a imagem do tema personalizado.  |
|\<CustomThemeColor\>   |Contêiner   ||Contêiner para os \<valores\>RedComponent \<,\>GreenComponent e \<BlueComponent\> . Esses valores são obrigatórios ao usar um tema personalizado.   |
|\<RedComponent\>   |Byte (0-255)   ||Representa o componente da cor vermelha.   |
|\<GreenComponent\>   |Byte (0-255)   ||Representa o componente da cor verde.   |
|\<BlueComponent\>   |Byte (0-255)   ||Representa o componente da cor azul.   |
| | | |
   
&#x2776; todos os elementos de primeiro nível são opcionais. Se um elemento de primeiro nível for omitido, todos os seus parâmetros filho permanecerão inalterados no dispositivo.
  
&#x2777; um sinalizador booliano pode ser qualquer um destes: true, false, 0 ou 1. Os valores boolianos ou numéricos deixados vazios podem fazer com que o XML fique defeituoso, então as configurações não seriam alteradas.
  
 &#x2778; se um parâmetro de cadeia de caracteres estiver presente, vazio e vazio for um valor válido, o parâmetro será limpo no dispositivo.
  
## <a name="manage-console-settings-using-an-xml-configuration-file"></a>Gerenciar as configurações do console usando um arquivo de configuração XML

Na inicialização, se um console de salas do Microsoft Teams encontrar um arquivo XML chamado SkypeSettings. xml no local **C:\Users\Skype\AppData\Local\Packages\Microsoft.SkypeRoomSystem_8wekyb3d8bbwe\LocalState**, ele aplicará as definições de configuração indicado pelo arquivo XML e exclua o arquivo XML.
  
Dependendo de quantas salas do Microsoft Teams sua empresa tem e como você opta por gerenciar para configurá-los, há várias maneiras de colocar o arquivo de configuração XML. Quando o arquivo for enviado por push para o console, reinicie-o para processar as alterações de configuração. O arquivo de configuração XML é excluído após seu processamento bem-sucedido. Os métodos de gerenciamento sugeridos para os dispositivos de salas do Microsoft Teams são discutidos em:
  
- [Configurando a política de grupo para salas do Microsoft Teams](room-systems-v2-operations.md#GroupPolicy)
    
- [Gerenciamento remoto usando o PowerShell](room-systems-v2-operations.md#RemotePS) e [configurar um item de arquivo](https://technet.microsoft.com/library/cc772536%28v=ws.11%29.aspx)
    
Você pode usar o método de sua preferência, desde que possa usá-lo para transferir arquivos e disparar a reinicialização do dispositivo de console. O arquivo deve ser legível, gravável e Delete-habilitado pela conta de usuário local do dispositivo (de preferência, deve ser de propriedade e ter privilégios totais concedidos a esse usuário). Se as permissões do arquivo não forem definidas corretamente, o software pode não conseguir aplicar as configurações, pode não conseguir excluir o arquivo após o processamento bem-sucedido e, possivelmente, pode até falhar.
  
## <a name="custom-theme-images"></a>Imagens de tema personalizado
<a name="Themes"> </a>

O arquivo de imagem do tema personalizado deve ser colocado no **C:\Users\Skype\AppData\Local\Packages\Microsoft.SkypeRoomSystem_8wekyb3d8bbwe\LocalState**, basta digitar o nome do arquivo e \<a\> extensão na variável CustomThemeImageUrl.
  
O arquivo de imagem deve ter exatamente 3840 X 1080 pixels e deve estar em um dos seguintes formatos de arquivo: jpg, jpeg, png e bmp. Se a sua organização quiser uma imagem personalizada, um designer de elementos gráficos encontrará um [modelo de tema personalizado do Photoshop](https://go.microsoft.com/fwlink/?linkid=870441) que seja útil. Ele contém mais detalhes sobre onde colocar vários elementos em uma imagem de tema e quais áreas aparecem em consoles e telas.
  
O arquivo de configuração XML deve ser atualizado na inicialização do dispositivo para reconhecer a imagem de tema. Depois que o novo arquivo XML for processado e excluído, o arquivo gráfico do tema será excluído do diretório.
  
## <a name="see-also"></a>Confira também


[Gerenciar Salas do Microsoft Teams](skype-room-systems-v2.md)

[Configurar um item de arquivo](https://technet.microsoft.com/library/cc772536%28v=ws.11%29.aspx)
