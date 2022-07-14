---
title: Interoperabilidade de vídeo na nuvem para o Microsoft Teams
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.topic: conceptual
ms.service: msteams
audience: admin
search.appverid: MET150
ms.reviewer: naforer
f1.keywords:
- NOCSH
description: Use a Interoperabilidade de Vídeo na Nuvem como uma solução intermediária para permitir que dispositivos de sala de reunião de terceiros participem de reuniões do Microsoft Teams.
ms.localizationpriority: medium
ms.collection:
- M365-voice
- M365-collaboration
ms.custom:
- seo-marvel-apr2020
- seo-marvel-mar2020
appliesto:
- Microsoft Teams
ms.openlocfilehash: 91ec337ad94341e20b07cd376be5156a526d8cd0
ms.sourcegitcommit: 0dda332951df3b946097d90a4923eb191fd86b4c
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/14/2022
ms.locfileid: "66789356"
---
# <a name="cloud-video-interop-for-microsoft-teams"></a>Interoperabilidade de vídeo na nuvem para o Microsoft Teams

A CVI (Interoperabilidade de Vídeo na Nuvem) é uma solução de terceiros qualificada da Microsoft que permite que salas de reunião de terceiros (telepresência) e VTCs (dispositivos de vídeo pessoais) participem de reuniões do Microsoft Teams.
 
Com o Microsoft Teams, você obtém colaboração avançada de conteúdo online em reuniões que incluem áudio, vídeo e compartilhamento de conteúdo. Isso pode ser apreciado por meio da área de trabalho e do cliente Web, bem como por meio de muitos dispositivos parceiros que se integram nativamente ao Microsoft Teams. No entanto, muitos clientes já investiram em dispositivos de teleconferência de vídeo e comunicação de vídeo pessoal, o que pode ser caro para atualizar. A Interoperabilidade de Vídeo na Nuvem fornece uma solução fácil, permitindo que você continue usando suas soluções existentes até que esteja pronto para atualizar.

Com a Interoperabilidade de Vídeo na Nuvem, o Microsoft Teams oferece uma experiência de reunião nativa para todos os participantes – em salas de reunião ou dentro de clientes do Teams.

### <a name="is-cloud-video-interop-for-me"></a>A Interoperabilidade de Vídeo na Nuvem é para mim?

A Interoperabilidade de Vídeo na Nuvem fornece um serviço intermediário enquanto você faz a transição para uma Solução nativa completa do Microsoft Teams, usando pontos de extremidade do Teams. O serviço fornecido deve fazer parte do caminho de migração.

A Interoperabilidade de Vídeo na Nuvem destina-se a clientes que atendem aos seguintes critérios:

- Ter uma grande implantação de dispositivos de sala de reunião e implantação de dispositivos de vídeo pessoais (mais de 50 dispositivos) que não estão qualificados para integração direta com o Microsoft Teams
- Têm suporte de um de nossos parceiros de Interoperabilidade de Vídeo na Nuvem
- Deseja manter o valor de seu investimento em seus dispositivos atuais de sala de reunião e dispositivos de vídeo pessoais durante a migração para uma solução nativa do Microsoft Teams

Embora a Interoperabilidade de Vídeo na Nuvem forneça uma ótima solução intermediária, incentivamos nossos clientes a examinar nossas soluções nativas de Reunião do Teams, como Sistemas de Salas do Teams, a longo prazo. 

### <a name="office-365-us-government-and-third-party-services"></a>Office 365 governo dos EUA e serviços de terceiros

Office 365 oferece a capacidade de integrar aplicativos de terceiros a sites do SharePoint Online, Skype for Business, Teams, aplicativos do Office incluídos no Microsoft 365 Apps para Grandes Empresas (como Word, Excel, PowerPoint e Outlook) e Outlook Web App. Além disso, o Office 365 dá suporte à integração com provedores de serviços de terceiros. Esses aplicativos e serviços de terceiros podem envolver o armazenamento, a transmissão e o processamento dos dados do cliente da sua organização em sistemas de terceiros que estão fora da infraestrutura do Office 365 e, portanto, não são cobertos pelos compromissos de conformidade e proteção de dados do Office 365. **É recomendável que você examine as declarações de privacidade e conformidade fornecidas por terceiros ao avaliar o uso apropriado desses serviços para sua organização.**



### <a name="partners-certified-for-microsoft-teams"></a>Parceiros certificados para o Microsoft Teams

Os parceiros a seguir têm soluções de interoperabilidade de vídeo para o Microsoft Teams. Sua empresa pode optar por trabalhar com qualquer combinação desses parceiros em sua empresa. 

|Parceiro|Solução de parceiro|
|----|---|
|![O logotipo que representa o Poly RealConnect.](media/polycom.png) | <a href="https://aka.ms/PolycomRealConnect" target="_blank">Poly RealConnect Service</a> |
|![O logotipo que representa o Pexip Infinity.](media/pexip.png)| <a href="https://aka.ms/PexipInfinity" target="_blank">Pexip Infinity para Microsoft Teams</a> | 
|![O logotipo que representa o Gateway do BlueJeans.](media/bluejeans.png)| <a href="https://aka.ms/BluejeansGateway" target="_blank">Gateway do BlueJeans para Microsoft Teams</a> |
|![O logotipo que representa o Cisco CVI.](media/cisco.png)|<a href="https://aka.ms/CiscoCVI" target="_blank">Integração de vídeo do Cisco Webex para o Microsoft Teams</a>|

### <a name="cloud-video-interop-overview"></a>Visão geral da Interoperabilidade de Vídeo na Nuvem

A Interoperabilidade de Vídeo na Nuvem é um serviço de terceiros que é oferecido por nossos parceiros para fornecer interoperabilidade entre as soluções de dispositivos de vídeo pessoais e de videoconferência existentes no local e o Microsoft Teams.

As soluções oferecidas por nossos parceiros consistem em componentes que podem ser implantados totalmente baseados em nuvem ou parcialmente/totalmente locais. 
     
O diagrama a seguir mostra a arquitetura de alto nível de nossas soluções de parceiros.

![Diagrama que descreve uma solução de parceiro de Interoperabilidade de Vídeo na Nuvem do Teams.](media/teams-cloud-video-interop-partner-solution.png)


## <a name="deploy-cloud-video-interop"></a>Implantar Interoperabilidade de Vídeo na Nuvem

Ao implantar uma solução de Interoperabilidade de Vídeo na Nuvem, é importante entender que você está implantando uma solução de parceiro. As etapas gerais que você deve seguir para implantar a Interoperabilidade de Vídeo na Nuvem estão listadas no diagrama a seguir.

![Diagrama que descreve a implantação de CVI em sua organização.](media/deploying-cvi.png)

### <a name="plan"></a>Plano

Durante a fase de plano, você deve identificar os dispositivos que não substituirão por um dispositivo nativo do Teams e encontrar um parceiro de Interoperabilidade de Vídeo na Nuvem que possa dar suporte a esses dispositivos.  

Também é importante entender que você precisará de uma licença para cada usuário que agendará reuniões nas quais você deseja que um dispositivo habilitado para Interoperabilidade de Vídeo na Nuvem ingresse. Observe que os requisitos exatos de licenciamento podem ser obtidos do parceiro cloud video Interop. Verifique se isso está claro antes de iniciar a implantação.

### <a name="configure"></a>Configuração

O parceiro que você escolheu para sua implantação de CVI fornecerá um documento de implantação completo que consiste em todas as etapas necessárias para implantar com êxito em sua organização. Isso incluirá portas de firewall e intervalos de IP, alterações de configuração para seus dispositivos e outras configurações que precisam ser alteradas.

### <a name="provision"></a>Disposição  

Durante a fase de provisionamento, você atribuirá licenças aos usuários apropriados de acordo com o guia de configuração do parceiro. Você também precisará passar pelo processo de Consentimento do Azure para fornecer ao parceiro acesso ao seu ambiente do Teams. Consulte [Permissões e consentimento no ponto de extremidade plataforma de identidade da Microsoft para](/azure/active-directory/develop/v2-permissions-and-consent) obter mais informações sobre o processo de consentimento do Azure.

### <a name="schedule"></a>Agenda

Depois que um usuário estiver habilitado para a Interoperabilidade de Vídeo na Nuvem, qualquer reunião agendada usando o Suplemento de Reunião do Teams para Outlook ou o Cliente do Teams terá as informações adicionais apropriadas adicionadas automaticamente à reunião do Teams para que os dispositivos compatíveis com a Interoperabilidade de Vídeo na Nuvem possam ingressar nessas reuniões.

### <a name="join"></a>Ingressar

Dependendo da solução de parceiro, há várias maneiras de ingressar em uma reunião habilitada para Interoperabilidade de Vídeo na Nuvem. Os cenários exatos de ingresso na reunião serão fornecidos pelo seu parceiro de Interoperabilidade de Vídeo na Nuvem. Listamos alguns exemplos abaixo:

- IVR (Resposta de Voz Interativa) 
  - Você pode discar para a IVR do parceiro usando o tenantkey@domain.
  - Quando estiver no IVR do parceiro, você será solicitado a inserir a conferenceId do VTC, que o conectará à reunião do Teams.
- Discagem direta 
  - Você pode discar diretamente para a reunião do Teams sem interagir com o IVR do parceiro usando o recurso de discagem direta, usando a cadeia de caracteres completa de tenantkey. VTC ConferenceId@domain.
- Discagem de um toque 
  - Se você tiver uma sala integrada do Teams, poderá usar os recursos de discagem de um toque oferecidos pelo seu parceiro (sem a necessidade de digitar nenhuma cadeia de caracteres de discagem).

## <a name="manage-cloud-video-interop"></a>Gerenciar Interoperabilidade de Vídeo na Nuvem

Depois que a Interoperabilidade de Vídeo na Nuvem for implantada, você poderá gerenciar os dispositivos usando as soluções fornecidas por nossos parceiros. Cada parceiro fornecerá uma interface administrativa que incluirá gerenciamento de licença e dispositivo. 

Os relatórios também estão disponíveis diretamente na interface administrativa do parceiro. Para obter mais informações sobre recursos de relatório, entre em contato com o parceiro de sua escolha. 

### <a name="troubleshooting-cloud-video-interop"></a>Solução de problemas de interoperabilidade de vídeo na nuvem

A Interoperabilidade de Vídeo na Nuvem é um serviço fornecido pelo parceiro. Se você estiver enfrentando problemas, a primeira etapa é conectar um dispositivo que tenha o Cliente do Teams instalado e conectá-lo ao mesmo segmento que o dispositivo cloud video Interop que está causando problemas. 

Se o Teams funcionar corretamente nesse segmento e você também tiver seguido todas as diretrizes de rede e configuração que o parceiro forneceu, você precisará entrar em contato com o parceiro para obter mais soluções de problemas. 

## <a name="powershell-for-cloud-video-interop"></a>Interoperabilidade de Vídeo do PowerShell para Nuvem

Os cmdlets do PowerShell a seguir estão disponíveis para automatizar (parcialmente) a implantação da Interoperabilidade de Vídeo na Nuvem.

- **Get-CsTeamsVideoInteropServicepolicy**: a Microsoft fornece políticas pré-construídas para cada um dos nossos parceiros com suporte que permitem que você designe quais parceiros usar para a Interoperabilidade de Vídeo na Nuvem.<br>Esse cmdlet permite identificar as políticas pré-construídas que você pode usar em sua organização. Você pode atribuir essa política a um ou mais de seus usuários aproveitando o cmdlet Grant-CsTeamsVideoInteropServicePolicy aplicativo.
- **Grant-CsTeamsVideoInteropServicePolicy**: esse cmdlet permite atribuir uma política predefinida para uso em sua organização ou atribuir a política a usuários específicos.
- **New-CsVideoInteropServiceProvider**: use este cmdlet para especificar informações sobre um parceiro CVI com suporte que sua organização gostaria de usar.
- **Set-CsVideoInteropServiceProvider**: use este cmdlet para atualizar informações sobre um parceiro CVI com suporte que sua organização usa.
- **Get-CsVideoInteropServiceProvider**: use este cmdlet para obter todos os provedores que foram configurados para uso na organização.
- **Remove-CsVideoInteropServiceProvider**: use este cmdlet para remover todas as informações do provedor sobre um provedor que sua organização não usa mais.