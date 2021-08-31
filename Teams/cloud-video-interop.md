---
title: Interoperabilidade de vídeo na nuvem para o Microsoft Teams
author: SerdarSoysal
ms.author: serdars
manager: serdars
ms.topic: conceptual
ms.service: msteams
audience: admin
search.appverid: MET150
ms.reviewer: naforer
f1.keywords:
- NOCSH
description: Use o Cloud Video Interop como uma solução intermediária para permitir que dispositivos de sala de reunião de terceiros participem Microsoft Teams reuniões.
ms.localizationpriority: medium
ms.collection:
- M365-voice
- M365-collaboration
ms.custom:
- seo-marvel-apr2020
- seo-marvel-mar2020
appliesto:
- Microsoft Teams
ms.openlocfilehash: 5e48b29ec04d10c899d646f4a28605e40fc2da09
ms.sourcegitcommit: 15e90083c47eb5bcb03ca80c2e83feffe67646f2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/30/2021
ms.locfileid: "58725500"
---
# <a name="cloud-video-interop-for-microsoft-teams"></a>Interoperabilidade de vídeo na nuvem para o Microsoft Teams

O Cloud Video Interop (CVI) é uma solução de terceiros qualificado pela Microsoft que permite que salas de reunião de terceiros (telepresência) e dispositivos de vídeo pessoal (VTCs) participem de reuniões Microsoft Teams de terceiros.
 
Com Microsoft Teams, você tem uma colaboração de conteúdo online rica em reuniões que incluem áudio, vídeo e compartilhamento de conteúdo. Isso pode ser aproveitado por meio da área de trabalho e do cliente Web, bem como por meio de muitos dispositivos parceiros que se integram de forma Microsoft Teams. No entanto, muitos clientes já investiram em dispositivos de comunicação de vídeo e vídeo pessoal, o que pode ser caro para atualizar. O Cloud Video Interop fornece uma solução fácil, permitindo que você continue usando suas soluções existentes até estar pronto para atualizar.

Com o Cloud Video Interop, Microsoft Teams oferece uma experiência de reunião nativa para todos os participantes – em salas de reunião ou dentro de Teams clientes.

### <a name="is-cloud-video-interop-for-me"></a>Cloud Video Interop é para mim?

O Cloud Video Interop fornece um serviço intermediário enquanto você faz a transição para uma solução Microsoft Teams nativa completa, usando Teams pontos de extremidade. O serviço fornecido deve fazer parte do seu caminho de migração.

O Cloud Video Interop destina-se aos clientes que atendem aos seguintes critérios:

- Ter uma grande implantação de dispositivos de sala de reunião e dispositivos de vídeo pessoal (50+ dispositivos) que não estão qualificados para integração direta com Microsoft Teams
- São suportados por um de nossos parceiros cloud video interop
- Deseja manter o valor de seu investimento em seus dispositivos de sala de reunião atuais e dispositivos de vídeo pessoal durante a migração para uma solução Microsoft Teams nativa

Embora o Cloud Video Interop fornece uma ótima solução intermediária, incentivamos nossos clientes a procurar em nossas soluções nativas de reunião do Teams, como Teams Room Systems, a longo prazo. 

### <a name="office-365-us-government-and-third-party-services"></a>Office 365 Us Government and third-party services

Office 365 oferece a capacidade de integrar aplicativos de terceiros em sites online do SharePoint, aplicativos Skype for Business, Teams, Office incluídos no Microsoft 365 Apps para Grandes Empresas (como Word, Excel, PowerPoint e Outlook) e Outlook Web App. Além disso, Office 365 oferece suporte à integração com provedores de serviços de terceiros. Esses aplicativos e serviços de terceiros podem envolver o armazenamento, a transmissão e o processamento dos dados do cliente da sua organização em sistemas de terceiros que estão fora da infraestrutura do Office 365 e, portanto, não são cobertos pelos compromissos de conformidade e proteção de dados do Office 365. **É recomendável que você revise as instruções de privacidade e conformidade fornecidas por terceiros ao avaliar o uso apropriado desses serviços para sua organização.**



### <a name="partners-certified-for-microsoft-teams"></a>Parceiros certificados para Microsoft Teams

Os parceiros a seguir têm soluções de interop de vídeo para Microsoft Teams. Sua empresa pode optar por trabalhar com qualquer combinação desses parceiros em sua empresa. 

|Parceiro|Solução de parceiro|
|----|---|
|![O logotipo que representa Poly RealConnect.](media/polycom.png) | <a href="https://aka.ms/PolycomRealConnect" target="_blank">Serviço Poly RealConnect</a> |
|![O logotipo que representa Pexip Infinity.](media/pexip.png)| <a href="https://aka.ms/PexipInfinity" target="_blank">Pexip Infinity para Microsoft Teams</a> | 
|![O logotipo que representa o Gateway BlueJeans.](media/bluejeans.png)| <a href="https://aka.ms/BluejeansGateway" target="_blank">Gateway BlueJeans para Microsoft Teams</a> |
|![O logotipo que representa o Cisco CVI.](media/cisco.png)|<a href="https://aka.ms/CiscoCVI" target="_blank">Integração de vídeo da Cisco Webex para Microsoft Teams</a>|

### <a name="cloud-video-interop-overview"></a>Visão geral de interop de vídeo na nuvem

O Cloud Video Interop é um serviço de terceiros oferecido por nossos parceiros para fornecer interoperabilidade entre soluções de dispositivos de vídeo e vídeo pessoal existentes no local e Microsoft Teams.

As soluções oferecidas por nossos parceiros consistem em componentes que podem ser implantados totalmente baseados em nuvem ou parcialmente/totalmente no local. 
     
O diagrama a seguir mostra a arquitetura de alto nível de nossas soluções de parceiros.

![Diagrama que descreve uma solução de Teams cloud video interop.](media/teams-cloud-video-interop-partner-solution.png)


## <a name="deploy-cloud-video-interop"></a>Implantar a interop de vídeo na nuvem

Ao implantar uma solução de Interop de Vídeo na Nuvem, é importante entender que você está implantando uma solução de parceiro. As etapas gerais que você deve seguir para implantar o Cloud Video Interop estão listadas no diagrama a seguir.

![Diagrama que descreve a implantação de CVI em sua organização.](media/deploying-cvi.png)

### <a name="plan"></a>Plano

Durante a fase de plano, você deve identificar os dispositivos que não substituirão por um dispositivo Teams nativo e encontrar um parceiro de Interop de Vídeo na Nuvem que possa dar suporte a esses dispositivos.  

Também é importante entender que você precisará de uma licença para cada usuário que agendar reuniões nas quais você deseja que um dispositivo habilitado para Cloud Video Interop participe. Observe que os requisitos exatos de licenciamento podem ser obtidos do parceiro cloud video interop. Certifique-se de que isso está claro antes de iniciar sua implantação.

### <a name="configure"></a>Configuração

O parceiro escolhido para sua implantação CVI fornecerá um documento de implantação completo que consiste em todas as etapas necessárias para implantar com êxito em sua organização. Isso incluirá portas de firewall e intervalos DE IP, alterações de configuração para seus dispositivos e outras configurações que precisam ser mudadas.

### <a name="provision"></a>Provisionamento  

Durante a fase de provisionamento, você atribuirá licenças aos usuários apropriados de acordo com o guia de configuração do parceiro. Você também precisará passar pelo processo de Consentimento do Azure para fornecer ao parceiro acesso ao seu Teams ambiente. Consulte [Permissões e consentimento no ponto de](/azure/active-directory/develop/v2-permissions-and-consent) extremidade plataforma de identidade da Microsoft para obter mais informações sobre o processo de consentimento do Azure.

### <a name="schedule"></a>Agendar

Depois que um usuário for habilitado para o Cloud Video Interop, qualquer reunião agendada usando o Complemento de Reunião do Teams para o Outlook ou o cliente do Teams terá as informações adicionais apropriadas adicionadas automaticamente à reunião do Teams para que dispositivos compatíveis com Cloud Video Interop possam participar dessas reuniões.

### <a name="join"></a>Ingressar

Dependendo da solução do parceiro, há várias maneiras de ingressar em uma reunião habilitada para Cloud Video Interop. Cenários exatos de junção de reuniões serão fornecidos pelo seu parceiro cloud video interop. Listamos alguns exemplos abaixo:

- IVR (Resposta Interativa de Voz) 
  - Você pode discar para a IVR do parceiro usando o tenantkey@domain.
  - Quando você estiver no IVR do parceiro, você será solicitado a inserir a conferência VTCId, que o conectará à reunião Teams.
- Discagem direta 
  - Você pode discar diretamente para a reunião Teams sem interagir com a IVR do parceiro usando o recurso de discagem direta, usando a cadeia de caracteres completa de tenantkey. VTC ConferenceId@domain.
- Discagem por toque único 
  - Se você tiver uma sala de Teams integrada, poderá usar os recursos de discagem de um toque oferecidos pelo parceiro (sem precisar digitar qualquer cadeia de caracteres de discagem).

## <a name="manage-cloud-video-interop"></a>Gerenciar a interop de vídeo na nuvem

Depois que o Cloud Video Interop for implantado, você poderá gerenciar os dispositivos usando as soluções fornecidas por nossos parceiros. Cada parceiro fornecerá uma interface administrativa que incluirá gerenciamento de licença e dispositivo. 

O relatório também está disponível diretamente na interface administrativa do parceiro. Para obter mais informações sobre recursos de relatórios, entre em contato com o parceiro de sua escolha. 

### <a name="troubleshooting-cloud-video-interop"></a>Solução de problemas de interop de vídeo na nuvem

Cloud Video Interop é um serviço fornecido pelo parceiro. Se você estiver enfrentando problemas, a primeira etapa é conectar um dispositivo que tenha o cliente Teams instalado e conectá-lo ao mesmo segmento que o dispositivo cloud video Interop que está causando problemas. 

Se Teams funciona corretamente neste segmento e você também seguiu todas as diretrizes de rede e configuração que o parceiro forneceu, você precisará entrar em contato com o parceiro para solução de problemas adicionais. 

## <a name="powershell-for-cloud-video-interop"></a>PowerShell para Interop de Vídeo na Nuvem

Os seguintes cmdlets do PowerShell estão disponíveis para você (parcialmente) automatizar a implantação de Cloud Video Interop.

- **Get-CsTeamsVideoInteropServicepolicy**: A Microsoft fornece políticas pré-construídas para cada um dos nossos parceiros com suporte que permitem que você designe quais parceiros usar para a Interop de Vídeo na Nuvem.<br>Este cmdlet permite identificar as políticas pré-construídas que você pode usar em sua organização. Você pode atribuir essa política a um ou mais de seus usuários aproveitando o cmdlet Grant-CsTeamsVideoInteropServicePolicy usuário.
- **Grant-CsTeamsVideoInteropServicePolicy**: Este cmdlet permite que você atribua uma política pré-construída para uso em sua organização ou atribua a política a usuários específicos.
- **New-CsVideoInteropServiceProvider**: Use este cmdlet para especificar informações sobre um parceiro CVI com suporte que sua organização gostaria de usar.
- **Set-CsVideoInteropServiceProvider**: Use este cmdlet para atualizar informações sobre um parceiro CVI com suporte que sua organização usa.
- **Get-CsVideoInteropServiceProvider**: Use este cmdlet para obter todos os provedores que foram configurados para uso na organização.
- **Remove-CsVideoInteropServiceProvider**: Use este cmdlet para remover todas as informações do provedor sobre um provedor que sua organização não usa mais.