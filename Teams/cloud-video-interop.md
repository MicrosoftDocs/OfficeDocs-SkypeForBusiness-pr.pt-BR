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
description: Use o Cloud Video Interop como uma solução intermediária para permitir que dispositivos de sala de reunião de terceiros participem de reuniões do Microsoft Teams.
localization_priority: Normal
ms.collection:
- M365-voice
- M365-collaboration
ms.custom:
- seo-marvel-apr2020
- seo-marvel-mar2020
appliesto:
- Microsoft Teams
ms.openlocfilehash: 2a9bf3cade5c17a8d3649a29ca999dec1f909624
ms.sourcegitcommit: 4386f4b89331112e0d54943dc3133791d5dca3fb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/09/2020
ms.locfileid: "49611845"
---
# <a name="cloud-video-interop-for-microsoft-teams"></a>Interoperabilidade de vídeo na nuvem para o Microsoft Teams

A Cloud Video Interop (CVI) é uma solução de terceiros qualificada da Microsoft que permite que salas de reunião de terceiros (telepresência) e dispositivos de vídeo pessoais (VTCs) insinuem reuniões do Microsoft Teams.
 
Com o Microsoft Teams, você tem uma colaboração rica em conteúdo online em reuniões que incluem áudio, vídeo e compartilhamento de conteúdo. Isso pode ser apreciado por meio da área de trabalho e do cliente Web, bem como por meio de muitos dispositivos parceiros que se integram de forma nativa ao Microsoft Teams. No entanto, muitos clientes já investiram em teleconferência em vídeo e em dispositivos de comunicação com vídeo pessoal, o que pode ser caro para atualizar. A Cloud Video Interop fornece uma solução fácil, permitindo que você continue usando suas soluções existentes até estar pronto para atualizar.

Com o Cloud Video Interop, o Microsoft Teams oferece uma experiência de reunião nativa para todos os participantes, em salas de reunião ou dentro de clientes do Teams.

### <a name="is-cloud-video-interop-for-me"></a>O Cloud Video Interop é para mim?

A Cloud Video Interop fornece um serviço intermediário enquanto você faz a transição para uma solução nativa do Microsoft Teams, usando pontos de extremidade do Teams. O serviço fornecido deve fazer parte do caminho de migração.

A Cloud Video Interop destina-se aos clientes que atendem aos seguintes critérios:

- Tenha uma grande implantação de dispositivos de sala de reunião e implantação de dispositivos de vídeo pessoais (mais de 50 dispositivos) que não estão qualificados para integração direta com o Microsoft Teams
- São suportados por um dos nossos parceiros cloud video Interop
- Deseja manter o valor de seu investimento em seus dispositivos atuais de sala de reunião e dispositivos de vídeo pessoais durante a migração para uma solução nativa do Microsoft Teams

Embora a Cloud Video Interop fornece uma ótima solução intermediária, incentivamos nossos clientes a procurar em nossas soluções nativas de Reunião do Teams, como o Teams Room Systems, a longo prazo. 

### <a name="office-365-us-government-and-third-party-services"></a>Office 365 US Government e serviços de terceiros

O Office 365 oferece a capacidade de integrar aplicativos de terceiros em sites do SharePoint Online, Skype for Business, Teams, aplicativos do Office incluídos nos Aplicativos do Microsoft 365 para empresas (como Word, Excel, PowerPoint e Outlook) e Outlook Web App. Além disso, o Office 365 dá suporte à integração com provedores de serviços de terceiros. Esses aplicativos e serviços de terceiros podem envolver armazenar, transmitir e processar dados de clientes da sua organização em sistemas de terceiros que estejam fora da infraestrutura do Office 365 e, portanto, não estão cobertos pelos compromissos de conformidade e proteção de dados do Office 365. **É recomendável que você revise as declarações de privacidade e conformidade fornecidas pelos terceiros ao avaliar o uso apropriado desses serviços para sua organização.**



### <a name="partners-certified-for-microsoft-teams"></a>Parceiros certificados para o Microsoft Teams

Os seguintes parceiros têm soluções de interop de vídeo para o Microsoft Teams. Sua empresa pode optar por trabalhar com qualquer combinação desses parceiros dentro da sua empresa. 

|Parceiro|Solução de parceiro|
|----|---|
|![O logotipo que representa Poly RealConnect](media/polycom.png) | <a href="https://aka.ms/PolycomRealConnect" target="_blank">Serviço Poly RealConnect</a> |
|![O logotipo que representa Pexip Infinity](media/pexip.png)| <a href="https://aka.ms/PexipInfinity" target="_blank">Pexip Infinity para Microsoft Teams</a> | 
|![O logotipo que representa o Gateway BlueJeans](media/bluejeans.png)| <a href="https://aka.ms/BluejeansGateway" target="_blank">Gateway BlueJeans para Microsoft Teams</a> |
|![O logotipo que representa Cisco CVI](media/cisco.png)|<a href="https://aka.ms/CiscoCVI" target="_blank">Cisco Webex Video Integration para Microsoft Teams</a>|

### <a name="cloud-video-interop-overview"></a>Visão geral do Cloud Video Interop

A Cloud Video Interop é um serviço de terceiros oferecido por nossos parceiros para fornecer interoperabilidade entre a videoconferência existente e as soluções de dispositivos de vídeo pessoais no local e o Microsoft Teams.

As soluções oferecidas por nossos parceiros consistem em componentes que podem ser implantados totalmente na nuvem com base ou parcialmente/totalmente no local. 
     
O diagrama a seguir mostra a arquitetura de alto nível das nossas soluções de parceiro.

![Diagrama descrevendo uma solução de parceiro do Teams Cloud Video Interop](media/teams-cloud-video-interop-partner-solution.png)


## <a name="deploy-cloud-video-interop"></a>Implantar o Cloud Video Interop

Ao implantar uma solução Cloud Video Interop, é importante compreender que você está implantando uma solução de parceiro. As etapas gerais que você deve seguir para implantar o Cloud Video Interop estão listadas no diagrama a seguir.

![Diagrama descrevendo a implantação de CVI em sua organização](media/deploying-cvi.png)

### <a name="plan"></a>Plano

Durante a fase do plano, você deve identificar os dispositivos que não substituirão por um dispositivo nativo do Teams e encontrar um parceiro cloud video Interop que possa dar suporte a esses dispositivos.  

Também é importante entender que você precisará de uma licença para cada usuário que agendar reuniões nas quais você deseja que um dispositivo habilitado para Cloud Video Interop participe. Observe que os requisitos exatos de licenciamento podem ser obtidos do parceiro Cloud Video Interop. Certifique-se de que isso está claro antes de iniciar a implantação.

### <a name="configure"></a>Configuração

O parceiro escolhido para sua implantação CVI fornecerá um documento de implantação completo que consiste em todas as etapas necessárias para a implantação com êxito em sua organização. Isso incluirá portas de firewall e intervalos IP, alterações de configuração para seus dispositivos e outras configurações que precisam ser mudadas.

### <a name="provision"></a>Disposição  

Durante a fase de provisionamento, você atribuirá licenças aos usuários apropriados de acordo com o guia de configuração do parceiro. Você também precisará passar pelo processo de Consentimento Do Azure para fornecer ao parceiro acesso ao seu ambiente do Teams. Consulte [Permissões e consentimento no ponto](https://docs.microsoft.com/azure/active-directory/develop/v2-permissions-and-consent) de extremidade da plataforma de identidade da Microsoft para obter mais informações sobre o processo de consentimento do Azure.

### <a name="schedule"></a>Agenda

Depois que um usuário é habilitado para o Cloud Video Interop, qualquer reunião agendada usando o Complemento de Reunião do Teams para Outlook ou o Cliente teams terá as informações adicionais apropriadas adicionadas automaticamente à reunião do Teams para que dispositivos compatíveis com Cloud Video Interop possam ingressar nessas reuniões.

### <a name="join"></a>Ingressar

Dependendo da solução do parceiro, há várias maneiras de ingressar em uma reunião habilitada para Cloud Video Interop. Cenários exatos de junção de reunião serão fornecidos pelo parceiro Cloud Video Interop. Listamos alguns exemplos abaixo:

- IVR (Resposta Interativa por Voz) 
  - Você pode discar para a IVR do parceiro usando o tenantkey@domain.
  - Quando estiver no IVR do parceiro, você será solicitado a inserir a ID da conferência VTC, que o conectará à reunião do Teams.
- Discagem direta 
  - Você pode discar diretamente para a reunião do Teams sem interagir com o IVR do parceiro usando o recurso de discagem direta, usando a cadeia completa de chaves de locatário. VTC ConferenceId@domain.
- Discagem com um toque 
  - Se você tiver uma sala integrada do Teams, poderá usar os recursos de discagem de um toque oferecidos por seu parceiro (sem precisar digitar qualquer cadeia de caracteres de discagem).

## <a name="manage-cloud-video-interop"></a>Gerenciar o Cloud Video Interop

Depois que a Cloud Video Interop for implantada, você poderá gerenciar os dispositivos usando as soluções fornecidas por nossos parceiros. Cada parceiro fornecerá uma interface administrativa que incluirá a licença e o gerenciamento de dispositivos. 

Os relatórios também estão disponíveis diretamente na interface administrativa do parceiro. Para obter mais informações sobre recursos de relatórios, entre em contato com o parceiro de sua escolha. 

### <a name="troubleshooting-cloud-video-interop"></a>Solução de problemas com o Cloud Video Interop

A Cloud Video Interop é um serviço fornecido pelo parceiro. Se você estiver enfrentando problemas, a primeira etapa é conectar um dispositivo que tenha o Cliente teams instalado e conectá-lo ao mesmo segmento que o dispositivo Cloud Video Interop que está causando problemas. 

Se o Teams funcionar corretamente neste segmento e você também tiver seguido todas as diretrizes de rede e configuração que o parceiro forneceu, você precisará entrar em contato com o parceiro para solucionar mais problemas. 

## <a name="powershell-for-cloud-video-interop"></a>PowerShell para Cloud Video Interop

Os seguintes cmdlets do PowerShell estão disponíveis para você automatizar (parcialmente) a implantação do Cloud Video Interop.

- **Get-CsTeamsVideoInteropServicepolicy:** a Microsoft fornece políticas pré-construídas para cada um dos nossos parceiros com suporte que permitem designar quais parceiros usar para a Cloud Video Interop.<br>Esse cmdlet permite identificar as políticas pré-construídas que você pode usar em sua organização. Você pode atribuir essa política a um ou mais usuários aproveitando o cmdlet Grant-CsTeamsVideoInteropServicePolicy usuário.
- **Grant-CsTeamsVideoInteropServicePolicy:** este cmdlet permite atribuir uma política pré-construída para uso em sua organização ou atribuir a política a usuários específicos.
- **New-CsVideoInteropServiceProvider:** use este cmdlet para especificar informações sobre um parceiro CVI com suporte que sua organização gostaria de usar.
- **Set-CsVideoInteropServiceProvider:** use este cmdlet para atualizar informações sobre um parceiro CVI com suporte que sua organização usa.
- **Get-CsVideoInteropServiceProvider:** use este cmdlet para obter todos os provedores que foram configurados para uso dentro da organização.
- **Remove-CsVideoInteropServiceProvider:** use este cmdlet para remover todas as informações do provedor sobre um provedor que sua organização não usa mais.
