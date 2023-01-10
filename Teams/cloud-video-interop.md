---
title: Interoperabilidade de vídeo na nuvem para o Microsoft Teams
ms.author: mabond
author: mkbond007
manager: serdars
ms.topic: conceptual
ms.service: msteams
audience: admin
search.appverid: MET150
ms.reviewer: naforer
f1.keywords:
- NOCSH
description: Use o Cloud Video Interop como uma solução intermediária para permitir que dispositivos de sala de reunião de terceiros participem de reuniões do Microsoft Teams.
ms.localizationpriority: medium
ms.collection:
- M365-voice
- M365-collaboration
ms.custom:
- seo-marvel-apr2020
- seo-marvel-mar2020
appliesto:
- Microsoft Teams
ms.openlocfilehash: 37201c788618da1544d4f00b743907dc22ff6366
ms.sourcegitcommit: 1398c778e46b0d81c9710cd70d3818a2b7af995a
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/09/2023
ms.locfileid: "69749007"
---
# <a name="cloud-video-interop-for-microsoft-teams"></a>Interoperabilidade de vídeo na nuvem para o Microsoft Teams

O CVI (Cloud Video Interop) é uma solução de terceiros qualificada pela Microsoft que permite que salas de reunião de terceiros (telepresença) e dispositivos de vídeo pessoais (VTCs) participem de reuniões do Microsoft Teams.
 
Com o Microsoft Teams, você obtém uma colaboração de conteúdo online avançada em reuniões que incluem áudio, vídeo e compartilhamento de conteúdo. Isso pode ser apreciado por meio da área de trabalho e do cliente Web, bem como por meio de muitos dispositivos parceiros que se integram nativamente ao Microsoft Teams. No entanto, muitos clientes já investiram em teleconferência de vídeo e dispositivos de comunicação de vídeo pessoal, o que pode ser caro para atualizar. O Cloud Video Interop fornece uma solução fácil, permitindo que você continue usando suas soluções existentes até estar pronto para atualizar.

Com o Cloud Video Interop, o Microsoft Teams oferece uma experiência de reunião nativa para todos os participantes – em salas de reunião ou dentro de clientes do Teams.

### <a name="is-cloud-video-interop-for-me"></a>O Cloud Video Interop é para mim?

O Cloud Video Interop fornece um serviço intermediário enquanto você faz a transição para uma solução nativa do Microsoft Teams, usando pontos de extremidade do Teams. O serviço fornecido deve fazer parte do caminho de migração.

O Cloud Video Interop destina-se aos clientes que atendem aos seguintes critérios:

- Tenha uma grande implantação de dispositivos de sala de reunião e implantação de dispositivos de vídeo pessoais (mais de 50 dispositivos) que não estão qualificados para integração direta com o Microsoft Teams
- Há suporte para um de nossos parceiros do Cloud Video Interop
- Deseja manter o valor de seu investimento em seus dispositivos de sala de reunião atuais e dispositivos de vídeo pessoais durante a migração para uma solução nativa do Microsoft Teams

Embora o Cloud Video Interop forneça uma ótima solução intermediária, incentivamos nossos clientes a investigar nossas soluções nativas de Reunião do Teams, como Sistemas de Sala do Teams, a longo prazo. 

### <a name="office-365-us-government-and-third-party-services"></a>Office 365 governo dos EUA e serviços de terceiros

Office 365 fornece a capacidade de integrar aplicativos de terceiros em sites do SharePoint Online, Skype for Business, Teams, aplicativos do Office incluídos em Microsoft 365 Apps para Grandes Empresas (como Word, Excel, PowerPoint e Outlook) e Outlook Web App. Além disso, Office 365 dá suporte à integração com provedores de serviços de terceiros. Esses aplicativos e serviços de terceiros podem envolver o armazenamento, a transmissão e o processamento dos dados do cliente da sua organização em sistemas de terceiros que estão fora da infraestrutura de Office 365 e, portanto, não são cobertos pelos compromissos de conformidade e proteção de dados Office 365. **É recomendável que você examine as instruções de privacidade e conformidade fornecidas por terceiros ao avaliar o uso apropriado desses serviços para sua organização.**

> [!NOTE]
> O Conector do Pexip Teams deve ser hospedado nas regiões do Arizona ou Texas Azure para o GCC High. A região do Azure da Virgínia não dá suporte à hospedagem do Conector do Pexip Teams para GCC High.

### <a name="partners-certified-for-microsoft-teams"></a>Parceiros certificados para o Microsoft Teams

Os parceiros a seguir têm soluções de interoperabilidade de vídeo para o Microsoft Teams. Sua empresa pode optar por trabalhar com qualquer combinação desses parceiros em sua empresa. 

|Parceiro|Solução de parceiro|
|----|---|
|![O logotipo que representa Poly RealConnect.](media/polycom.png) | <a href="https://aka.ms/PolycomRealConnect" target="_blank">Serviço Poly RealConnect</a> |
|![O logotipo que representa o Pexip Infinity.](media/pexip.png)| <a href="https://aka.ms/PexipInfinity" target="_blank">Pexip Infinity para Microsoft Teams</a> | 
|![O logotipo que representa o BlueJeans Gateway.](media/bluejeans.png)| <a href="https://aka.ms/BluejeansGateway" target="_blank">BlueJeans Gateway para Microsoft Teams</a> |
|![O logotipo que representa o Cisco CVI.](media/cisco.png)|<a href="https://aka.ms/CiscoCVI" target="_blank">Integração de vídeo do Cisco Webex para o Microsoft Teams</a>|

### <a name="cloud-video-interop-overview"></a>Visão geral do Cloud Video Interop

O Cloud Video Interop é um serviço de terceiros que é oferecido por nossos parceiros para fornecer interoperabilidade entre a conferência de vídeo existente e soluções de dispositivos de vídeo pessoais no local e o Microsoft Teams.

As soluções oferecidas por nossos parceiros consistem em componentes que podem ser implantados totalmente baseados em nuvem ou parcialmente/totalmente no local. 
     
O diagrama a seguir mostra a arquitetura de alto nível de nossas soluções de parceiros.

![Diagrama que descreve uma solução de parceiro do Teams Cloud Video Interop.](media/teams-cloud-video-interop-partner-solution.png)


## <a name="deploy-cloud-video-interop"></a>Implantar o Cloud Video Interop

Ao implantar uma solução do Cloud Video Interop, é importante entender que você está implantando uma solução de parceiro. As etapas gerais que você deve tomar para implantar o Cloud Video Interop estão listadas no diagrama a seguir.

![Diagrama que descreve a implantação do CVI em sua organização.](media/deploying-cvi.png)

### <a name="plan"></a>Plano

Durante a fase de plano, você deve identificar os dispositivos que não substituirá por um dispositivo nativo do Teams e encontrar um parceiro do Cloud Video Interop que possa dar suporte a esses dispositivos.  

Também é importante entender que você precisará de uma licença para cada usuário que agendará reuniões nas quais você deseja ingressar um dispositivo habilitado para Cloud Video Interop. Observe que os requisitos exatos de licenciamento podem ser obtidos do parceiro do Cloud Video Interop. Verifique se isso está claro antes de iniciar sua implantação.

### <a name="configure"></a>Configuração

O parceiro escolhido para a implantação do CVI fornecerá um documento de implantação completo que consiste em todas as etapas necessárias para implantar com êxito em sua organização. Isso incluirá portas de firewall e intervalos de IP, alterações de configuração para seus dispositivos e outras configurações que precisam ser alteradas.

### <a name="provision"></a>Disposição  

Durante a fase de provisionamento, você atribuirá licenças aos usuários apropriados de acordo com o guia de configuração do parceiro. Você também precisará passar pelo processo de Consentimento do Azure para fornecer o acesso do parceiro ao seu ambiente do Teams. Consulte [Permissões e consentimento no ponto de extremidade plataforma de identidade da Microsoft](/azure/active-directory/develop/v2-permissions-and-consent) para obter mais informações sobre o processo de consentimento do Azure.

### <a name="schedule"></a>Agenda

Depois que um usuário estiver habilitado para o Cloud Video Interop, qualquer reunião agendada usando o Suplemento de Reunião do Teams para Outlook ou o Cliente do Teams terá as informações adicionais apropriadas adicionadas automaticamente à reunião do Teams para que dispositivos compatíveis com o Cloud Video possam participar dessas reuniões.

### <a name="join"></a>Ingressar

Dependendo da solução de parceiro, há várias maneiras de ingressar em uma reunião habilitada para Cloud Video Interop. Os cenários exatos de junção de reunião serão fornecidos pelo parceiro do Cloud Video Interop. Listamos alguns exemplos abaixo:

- IVR (Resposta interativa de voz) 
  - Você pode discar no IVR do parceiro usando o tenantkey@domain.
  - Quando você estiver no IVR do parceiro, será solicitado que você insira a conferenceId do VTC, que o conectará à reunião do Teams.
- Discagem direta 
  - Você pode discar diretamente para a reunião do Teams sem interagir com o IVR do parceiro usando o recurso de discagem direta, usando a cadeia de caracteres completa da chave de locatário. VTC ConferenceId@domain.
- Discagem de um toque 
  - Se você tiver uma sala integrada do Teams, poderá usar os recursos de discagem de um toque oferecidos pelo seu parceiro (sem a necessidade de digitar qualquer cadeia de caracteres de discagem).

## <a name="manage-cloud-video-interop"></a>Gerenciar interoperabilidade de vídeo na nuvem

Depois que o Cloud Video Interop for implantado, você poderá gerenciar os dispositivos usando as soluções fornecidas por nossos parceiros. Cada parceiro fornecerá uma interface administrativa que incluirá licença e gerenciamento de dispositivos. 

O relatório também está disponível diretamente na interface administrativa do parceiro. Para obter mais informações sobre recursos de relatório, entre em contato com o parceiro de sua escolha. 

### <a name="troubleshooting-cloud-video-interop"></a>Solução de problemas de interoperabilidade de vídeo na nuvem

O Cloud Video Interop é um serviço fornecido pelo parceiro. Se você estiver enfrentando problemas, a primeira etapa é conectar um dispositivo que tenha o Cliente do Teams instalado e conectá-lo ao mesmo segmento que o dispositivo Cloud Video Interop que está causando problemas. 

Se o Teams funcionar corretamente neste segmento e você também tiver seguido todas as diretrizes de rede e configuração fornecidas pelo parceiro, você precisará entrar em contato com o parceiro para obter mais soluções de problemas. 

## <a name="powershell-for-cloud-video-interop"></a>Interoperabilidade do PowerShell for Cloud Video

Os cmdlets do PowerShell a seguir estão disponíveis para você automatizar (parcialmente) a implantação do Cloud Video Interop.

- **Get-CsTeamsVideoInteropServicepolicy**: a Microsoft fornece políticas pré-construídas para cada um de nossos parceiros com suporte que permitem designar quais parceiros usar para o Cloud Video Interop.<br>Esse cmdlet permite identificar as políticas pré-construídas que você pode usar em sua organização. Você pode atribuir essa política a um ou mais usuários aproveitando o cmdlet Grant-CsTeamsVideoInteropServicePolicy.
- **Grant-CsTeamsVideoInteropServicePolicy**: este cmdlet permite atribuir uma política pré-construída para uso em sua organização ou atribuir a política a usuários específicos.
- **New-CsVideoInteropServiceProvider**: use este cmdlet para especificar informações sobre um parceiro CVI com suporte que sua organização gostaria de usar.
- **Set-CsVideoInteropServiceProvider**: use este cmdlet para atualizar informações sobre um parceiro CVI com suporte que sua organização usa.
- **Get-CsVideoInteropServiceProvider**: use este cmdlet para obter todos os provedores que foram configurados para uso na organização.
- **Remove-CsVideoInteropServiceProvider**: use este cmdlet para remover todas as informações do provedor sobre um provedor que sua organização não usa mais.
