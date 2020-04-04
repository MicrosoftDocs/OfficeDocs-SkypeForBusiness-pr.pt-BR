---
title: Gerenciar remotamente as configurações de dispositivo de salas do Microsoft Teams
ms.author: v-lanac
author: lanachin
ms.reviewer: sohailta
manager: serdars
audience: ITPro
ms.topic: article
ms.service: msteams
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: df418e25-81fd-474d-be16-5cd1ac8145cc
ms.collection:
- M365-collaboration
ms.custom: seo-marvel-mar2020
description: Gerenciamento remoto das configurações padrão usadas por um dispositivo de salas do Microsoft Teams, incluindo a aplicação de um tema personalizado e a criação de um arquivo de configurações mestre.
ms.openlocfilehash: 988fa11ef3a84c21bfef3a726e3901bae26e222a
ms.sourcegitcommit: cddaacf1e8dbcdfd3f94deee7057c89cee0e5699
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/03/2020
ms.locfileid: "43140984"
---
# <a name="manage-a-microsoft-teams-rooms-console-settings-remotely-with-an-xml-configuration-file"></a>Gerenciar as configurações de um console de salas do Microsoft Teams remotamente com um arquivo de configuração XML

Este artigo discute o gerenciamento remoto das configurações padrão usadas por um dispositivo de salas do Microsoft Teams, incluindo a aplicação de um tema personalizado. Ele discute como criar um arquivo de configurações mestre e links para discussões sobre como colocá-los conforme necessário em dispositivos gerenciados remotamente.
  
É possível alterar as configurações padrão de dispositivos gerenciados remotamente atualizando um arquivo XML mestre e enviando cópias para os consoles gerenciados. Você também pode implementar temas personalizados em seus consoles de sala do Microsoft Teams com arquivos de configuração XML.
  
## <a name="create-an-xml-configuration-file"></a>Criar um arquivo de configuração XML

Qualquer editor de texto pode ser usado para criar um arquivo de configurações. A tabela de **elementos XML** explica os elementos mostrados neste arquivo de configuração de exemplo SkypeSettings. XML (nome do arquivo obrigatório).
  
```XML
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
    <DuplicateIngestDefault>false</DuplicateIngestDefault>
    <SendLogs>
        <EmailAddressForLogsAndFeedback>RanierConf@contoso.com</EmailAddressForLogsAndFeedback>
        <SendLogsAndFeedback>true</SendLogsAndFeedback>
    </SendLogs>
    <Devices>
        <MicrophoneForCommunication>Microsoft LifeChat LX-6000</MicrophoneForCommunication>
        <SpeakerForCommunication>Realtek High Definition Audio</SpeakerForCommunication>
        <DefaultSpeaker>Polycom CX5100</DefaultSpeaker>
        <ContentCameraId>USB\VID_046D&amp;PID_0843&amp;MI_00\7&amp;17446CF2&amp;0&amp;0000</ContentCameraId>
        <ContentCameraInverted>false</ContentCameraInverted>
        <ContentCameraEnhancement>true</ContentCameraEnhancement>
    </Devices>
    <Theming>
        <ThemeName>Custom</ThemeName>
        <CustomThemeImageUrl>file name</CustomThemeImageUrl>
        <CustomThemeColor>
            <RedComponent>100</RedComponent>
            <GreenComponent>100</GreenComponent>
            <BlueComponent>100</BlueComponent>
        </CustomThemeColor>
    </Theming>
</SkypeSettings>
```

Se um valor de variável for do tipo errado, os elementos estiverem fora da ordem, os elementos não serão fechados ou outro erro será encontrado, o arquivo XML estará *incorreto*. Durante o processamento de um arquivo XML mal formado, as configurações encontradas até o ponto em que o erro ocorre são aplicadas, e o restante do arquivo é ignorado. Todos os elementos desconhecidos do XML serão ignorados. Se um parâmetro for omitido, ele permanecerá inalterado no dispositivo. Se um valor de parâmetro for inválido, seu valor anterior permanecerá inalterado.
  
**Elementos XML**

|Elemento|Tipo|Nível|Uso|
|:--- |:--- |:--- |:--- |
|\<SkypeSettings\> |Contêiner para todos os elementos. ||Obrigatório. |
| \<AutoScreenShare\>  |&#x2777; Boolean  |Primeiro &#x2776;  | Se verdadeiro, o compartilhamento automático de tela será habilitado.  |
|\<HideMeetingName\> |&#x2777; Boolean  |Primeiro &#x2776;  |Se verdadeiro, os nomes das reuniões ficarão ocultos. |
|\<UserAccount\> |Contêiner |Primeiro &#x2776;  |Contêiner para os parâmetros de credenciais. O endereço de entrada, endereço do Exchange ou endereço de email geralmente é o mesmo, como RanierConf<span></span>@contoso. com. |
|\<SkypeMeetingsEnabled\>  |&#x2777; Boolean  |Primeiro &#x2776;  |Habilitado por padrão. |
|\<SkypeSignInAddress\> |Cadeia de caracteres &#x2778;  ||O nome de conexão para a conta de dispositivo do SfB ou do teams do console. |
|\<ExchangeAddress\> |Cadeia de caracteres &#x2778;  ||O nome de entrada da conta do dispositivo do Exchange no console. Se o ExchangeAddress for omitido, o SkypeSignInAddress não será reutilizado automaticamente. |
|\<DomainUsername\> |Cadeia de caracteres &#x2778;  ||O domínio e o nome do usuário do dispositivo de console, por exemplo, Seattle\RanierConf. |
|\<Passe\> |Cadeia de caracteres 3  || O parâmetro de senha é a mesma senha usada para entrar na conta do dispositivo do Skype for Business.   |
| \<ConfigureDomain\>  |Cadeia de caracteres &#x2778;  ||Você pode listar vários domínios, separados por vírgulas. |
|\<TeamsMeetingsEnabled\> |&#x2777; Boolean  |Primeiro &#x2776;  |Desabilitado por padrão. <br/> <br/> O arquivo XML é considerado mal formado se ambos \<os\> SkypeMeetingsEnabled\<e\> TeamsMeetingsEnabled estiverem desativados, mas é aceitável ter ambas as configurações habilitadas ao mesmo tempo. |
|\<IsTeamsDefaultClient> |&#x2777; Boolean  |Primeiro &#x2776;  |Desabilitado por padrão. |
|\<BluetoothAdvertisementEnabled> |&#x2777; Boolean  |Primeiro &#x2776;  |Habilitado por padrão. |
|\<DualScreenMode\>  |&#x2777; Boolean  |Primeiro &#x2776;  |Se verdadeiro, o modo de tela dupla está habilitado. Caso contrário, o dispositivo usa o modo de tela única. |
| \<DuplicateIngestDefault\> |&#x2777; Boolean  |Primeiro &#x2776; |Se verdadeiro, o conteúdo é mostrado nas duas telas no modo de tela dupla, quando estiver fora da reunião. | 
|\<SendLogs\> |Contêiner |Primeiro &#x2776;  |  |
|\<EmailAddressForLogsAndFeedback\> |Cadeia de caracteres &#x2778;  | | Define um endereço de email opcional para o qual os logs podem ser enviados quando a janela "fornecer comentários" for exibida. |
|\<SendLogsAndFeedback\> |&#x2777; Boolean  | | Se verdadeiro, os logs são enviados para o administrador. Se falso, somente os comentários são enviados para o administrador (e não os logs).  |
| \<Dispositivos\>  |Contêiner |Primeiro &#x2776;  | Os nomes dos dispositivos de áudio conectados nos elementos filho têm os mesmos valores listados no aplicativo Gerenciador de Dispositivos. A configuração pode conter um dispositivo que atualmente não existe no sistema, como um dispositivo de A/V que não está conectado ao console. A configuração seria mantida para o dispositivo correspondente.  |
|\<MicrophoneForCommunication\> |Cadeia de caracteres &#x2778;  ||Define o microfone usado como o dispositivo de gravação em uma conferência. |
|\<SpeakerForCommunication\> |Cadeia de caracteres &#x2778;  ||Dispositivo que deve ser usado como alto-falante para a conferência. Essa configuração é usada para definir o dispositivo de alto-falantes usado em uma chamada. |
|\<Defaultspeakr\> |Cadeia de caracteres &#x2778;  ||Dispositivo que deve ser usado para executar o áudio de uma fonte de ingestão HDMI.  |
|\<ContentCameraId>  | Cadeia de caracteres &#x2778;  | | Defina o caminho da instância da câmera configurada em sala para compartilhar conteúdo analógico do quadro de comunicações em uma reunião. Consulte [localizar o caminho da instância USB da câmera de conteúdo](#locate-the-content-camera-usb-instance-path).|
|\<ContentCameraInverted>  | &#x2777; Boolean | | Especifique se a câmera de conteúdo está fisicamente instalada de cabeça para baixo. Para câmeras de conteúdo que dão suporte à rotação automática, especifique falso. |
|\<ContentCameraEnhancement>  | &#x2777; Boolean | |Quando definida como true (o padrão), a imagem da câmera de conteúdo é aprimorada digitalmente: a borda do quadro de comunicações é detectada e um zoom apropriado é selecionado, as linhas de tinta são aprimoradas e a pessoa que está escrevendo no quadro de comunicações torna-se transparente.  <br><br> Defina como falso se você pretende enviar um RSS feed de vídeo para os participantes de uma reunião de espaços em que um quadro de comunicações não está desenhado com uma caneta e, em vez disso, a câmera é usada para mostrar notas autoadesivas, cartazes ou outras mídias.  |
| \<Temas\>  |Contêiner |Primeiro &#x2776;  |Um dos recursos que podem ser aplicados com um arquivo XML é um tema personalizado para a sua organização. Você pode especificar um nome de tema, uma imagem de fundo e uma cor. |
|\<ThemeName\> |Cadeia de caracteres &#x2778;  || Usado para identificar o tema no cliente. As opções de Nome do Tema são Padrão, um dos temas predefinidos fornecidos ou Personalizado. <br/>  Os nomes de temas personalizados sempre usam o nome *personalizado*. A interface do usuário do cliente pode ser definida no console com o padrão ou uma das predefinições, mas o uso de um tema personalizado deve ser definido remotamente por um administrador. <br/>  Os temas predefinidos incluem:  <br/>  Padrão <br/>  Onda Azul <br/>  Floresta Digital <br/>  Apanhador de Sonhos <br/>  Suco de Lima <br/>  Pixel Perfeito <br/>  Mapa Rodoviário <br/>  Pôr do Sol <br/>  Para desabilitar o tema atual, use "nenhum tema" para o ThemeName.  |
|\<CustomThemeImageUrl\> |Cadeia de caracteres &#x2778;  ||Obrigatório para um tema personalizado, caso contrário, opcional. Insira somente o nome do arquivo.   |Para obter mais informações sobre a imagem do tema personalizado, consulte a seção [imagens do tema personalizado](xml-config-file.md#Themes) .
|\<CustomThemeColor\> |Contêiner ||Contêiner para os \<valores\>RedComponent \<,\>GreenComponent e \<BlueComponent\> . Esses valores são necessários para um tema personalizado. |
|\<RedComponent\> |Byte (0-255) ||Representa o componente da cor vermelha. |
|\<GreenComponent\> |Byte (0-255) ||Representa o componente da cor verde. |
|\<BlueComponent\> |Byte (0-255) ||Representa o componente da cor azul. | 
| | | |

&#x2776; todos os elementos de primeiro nível são opcionais. Se um elemento de primeiro nível for omitido, todos os seus parâmetros filho permanecerão inalterados no dispositivo.
  
&#x2777; um sinalizador booliano pode ser: true, false, 0 ou 1. Deixar valores Boolean ou numéricos vazios pode renderizar o XML malformado e impedir alterações nas configurações.
  
&#x2778; se um parâmetro de cadeia de caracteres estiver presente e vazio e vazio for um valor válido, o parâmetro será limpo no dispositivo.
  
## <a name="manage-console-settings-with-an-xml-configuration-file"></a>Gerenciar as configurações do console usando um arquivo de configuração XML

Na inicialização, se um console de salas do Microsoft Teams encontrar um arquivo XML chamado SkypeSettings. `C:\Users\Skype\AppData\Local\Packages\Microsoft.SkypeRoomSystem_8wekyb3d8bbwe\LocalState`XML localizado em, ele aplicará as configurações indicadas pelo arquivo XML e excluirá o arquivo XML.
  
Dependendo de quantas salas do Microsoft Teams sua empresa tem e como você opta por gerenciar para configurá-los, há várias maneiras de colocar o arquivo de configuração XML. Quando o arquivo for enviado por push para o console, reinicie-o para processar as alterações de configuração. O arquivo de configuração XML é excluído após seu processamento bem-sucedido. Os métodos de gerenciamento sugeridos para os dispositivos de salas do Microsoft Teams são discutidos em:
  
- [Configurando a política de grupo para salas do Microsoft Teams](rooms-operations.md#GroupPolicy)
- [Gerenciamento remoto usando o PowerShell](rooms-operations.md#RemotePS) e [configurar um item de arquivo](https://technet.microsoft.com/library/cc772536%28v=ws.11%29.aspx)

Você pode usar o método de sua preferência, desde que possa usá-lo para transferir arquivos e disparar a reinicialização do dispositivo de console. O arquivo deve ser legível, gravável e Delete-habilitado pela conta de usuário local do dispositivo. Preferencialmente, ele é de propriedade e tem privilégios totais concedidos a esse usuário. Se as permissões de arquivo não estiverem definidas corretamente, o software pode falhar para aplicar as configurações, pode falhar ao excluir o arquivo após o processamento bem-sucedido, e até mesmo pode falhar.
  
## <a name="custom-theme-images"></a>Imagens de tema personalizado

<a name="Themes"> </a>

O arquivo de imagem do tema personalizado deve ser colocado`C:\Users\Skype\AppData\Local\Packages\Microsoft.SkypeRoomSystem_8wekyb3d8bbwe\LocalState` na pasta. Digite o nome do arquivo e a extensão \<na\> variável CustomThemeImageUrl.
  
O arquivo de imagem deve ser exatamente 3840X1080 pixels e deve ser um dos seguintes formatos de arquivo: jpg, JPEG, png e BMP. Se a sua organização quiser uma imagem personalizada, um designer de elementos gráficos poderá usar o [modelo do Photoshop de tema personalizado](../downloads/ThemingTemplateMicrosoftTeamsRooms_v2.1.psd). Ele contém mais detalhes sobre onde vários elementos da interface do usuário são relativos ao restante de uma imagem de tema e quais áreas aparecem em consoles e exibições.
  
O arquivo de configuração XML deve ser atualizado na inicialização do dispositivo para reconhecer a imagem de tema. Depois que o novo arquivo XML for processado e excluído, o arquivo gráfico do tema será excluído do diretório.
  
## <a name="locate-the-content-camera-usb-instance-path"></a>Localize o caminho da instância USB da câmera de conteúdo

Para localizar o caminho da instância:

1. Vá para configurações do Windows no console de salas do Microsoft Teams.
2. Digite a senha de administrador.
3. Em um prompt de comando, `devmgmt.msc` digite para exibir o Gerenciador de dispositivos.
4. No **Gerenciador de dispositivos**, procure no nó **dispositivos de imagem** e localize a câmera de conteúdo.
5. Clique com o botão direito do mouse na câmera e abra **Propriedades**.
6. Selecione a guia **detalhes** e localize a propriedade **caminho da instância do dispositivo** na lista suspensa.
7. O valor mostrado é o caminho da instância do dispositivo a ser definido no arquivo de configuração XML. Ao especificar o caminho em XML, substitua o "e" comercial ( `&amp;`&) por.

## <a name="see-also"></a>Confira também

[Câmeras de conteúdo](content-camera.md)

[Gerenciar Salas do Microsoft Teams](rooms-manage.md)

[Configurar um item de arquivo](https://technet.microsoft.com/library/cc772536%28v=ws.11%29.aspx)
