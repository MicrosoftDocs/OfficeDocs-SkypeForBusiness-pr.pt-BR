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
description: Use a interoperabilidade de vídeo em nuvem como uma solução intermediária para permitir que dispositivos de salas de reunião de terceiros ingressem em reuniões do Microsoft Teams.
localization_priority: Normal
ms.custom:
- seo-marvel-apr2020
ms.collection:
- M365-voice
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 7f812d27b07dadb2f60bf77302e18eb0879f977e
ms.sourcegitcommit: c79b83e03a89649e2b6e494a741a392819baf2d2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/13/2020
ms.locfileid: "48433065"
---
# <a name="cloud-video-interop-for-microsoft-teams"></a>Interoperabilidade de vídeo na nuvem para o Microsoft Teams

A interoperabilidade de vídeo em nuvem (CVI) é uma solução de terceiros qualificada pela Microsoft que permite que salas de reunião de terceiros (telepresença) e dispositivos de vídeo pessoais (VTCs) ingressem em reuniões do Microsoft Teams.
 
Com o Microsoft Teams, você obtém colaboração avançada de conteúdo online em reuniões que incluem áudio, vídeo e compartilhamento de conteúdo. Isso pode ser aproveitado pelo cliente da área de trabalho e da Web, bem como por vários dispositivos parceiros que se integram nativamente ao Microsoft Teams. No entanto, muitos clientes já investiram em dispositivos de videoconferência e de comunicação de vídeo pessoal, o que pode ser caro de fazer a atualização. A interoperabilidade de vídeo em nuvem oferece uma solução fácil, permitindo que você continue usando suas soluções existentes até estar pronto para fazer a atualização.

Com a interoperabilidade de vídeo em nuvem, o Microsoft Teams oferece uma experiência de reunião nativa para todos os participantes – em salas de reunião ou dentro de clientes do teams.

### <a name="is-cloud-video-interop-for-me"></a>A interoperabilidade de vídeo em nuvem para mim?

A interoperabilidade de vídeo em nuvem fornece um serviço intermediário enquanto você faz a transição para uma solução completa do Microsoft Teams, usando pontos de extremidade do teams. O serviço fornecido deve fazer parte do caminho de migração.

A interoperabilidade de vídeo em nuvem destina-se a clientes que atendem aos seguintes critérios:

- Há uma grande implantação de dispositivos da sala de reunião e a implantação de dispositivos de vídeo pessoal (mais de 50 dispositivos) que não são qualificados para a integração direta com o Microsoft Teams
- São compatíveis com um dos nossos parceiros de interoperabilidade de vídeo em nuvem
- Deseja manter o valor do investimento em seus dispositivos de sala de reunião e dispositivos de vídeo pessoais atuais durante a migração para uma solução nativa do Microsoft Teams

Embora a interoperabilidade de vídeo em nuvem forneça uma excelente solução intermediária, incentivamos nossos clientes a examinar nossas soluções de reunião de equipes nativas, como sistemas de sala de equipe, por longo prazo. 

### <a name="office-365-us-government-and-third-party-services"></a>Office 365 governo dos EUA e serviços de terceiros

O Office 365 fornece a capacidade de integrar aplicativos de terceiros a sites do SharePoint Online, Skype for Business, Teams, aplicativos do Office incluídos em aplicativos do Microsoft 365 para empresas (como o Word, o Excel, o PowerPoint e o Outlook) e o Outlook Web App. Além disso, o Office 365 dá suporte à integração com provedores de serviços terceirizados. Esses aplicativos e serviços de terceiros podem envolver o armazenamento, a transmissão e o processamento dos dados do cliente da sua organização em sistemas de terceiros que estão fora da infraestrutura do Office 365 e, portanto, não são cobertos pelos compromissos do Office 365 de conformidade e proteção de dados. **É recomendável que você revise as declarações de privacidade e conformidade fornecidas por terceiros ao avaliar o uso apropriado desses serviços para sua organização.**



### <a name="partners-certified-for-microsoft-teams"></a>Parceiros certificados para o Microsoft Teams

Os parceiros a seguir têm soluções de interoperabilidade de vídeo para Microsoft Teams. Sua empresa pode optar por trabalhar com qualquer combinação desses parceiros na sua empresa. 

|Sócio|Solução de parceiros|
|----|---|
|![O logotipo que representa Polycom RealConnect](media/polycom.png) | <a href="https://aka.ms/PolycomRealConnect" target="_blank">Serviço de RealConnect Polycom</a> |
|![O logotipo que representa o infinito Pexip](media/pexip.png)| <a href="https://aka.ms/PexipInfinity" target="_blank">Pexip infinito para Microsoft Teams</a> | 
|![O logotipo que representa o gateway BlueJeans](media/bluejeans.png)| <a href="https://aka.ms/BluejeansGateway" target="_blank">BlueJeans gateway para Microsoft Teams</a> |
|![O logotipo que representa o Cisco CVI](media/cisco.png)|<a href="https://aka.ms/CiscoCVI" target="_blank">Integração com vídeo Cisco WebEx para o Microsoft Teams</a>|

### <a name="cloud-video-interop-overview"></a>Visão geral da interoperabilidade em nuvem

A interoperabilidade de vídeo em nuvem é um serviço de terceiros oferecido pelos nossos parceiros para fornecer interoperabilidade entre as soluções de videoconferência e de vídeo pessoal existentes, no local e no Microsoft Teams.

As soluções oferecidas pelos nossos parceiros consistem em componentes que podem ser implantados completamente com base na nuvem ou parcialmente/totalmente no local. 
     
O diagrama a seguir mostra a arquitetura de alto nível de nossas soluções de parceiros.

![Diagrama descrevendo uma solução de parceiro de interoperabilidade de vídeo em nuvem](media/teams-cloud-video-interop-partner-solution.png)


## <a name="deploy-cloud-video-interop"></a>Implantar a interoperabilidade de vídeo em nuvem

Ao implantar uma solução de interoperabilidade de vídeo em nuvem, é importante compreender que você está implantando uma solução de parceiro. As etapas gerais necessárias para implantar a interoperabilidade de vídeo em nuvem estão listadas no diagrama a seguir.

![Diagrama descrevendo a implantação do CVI em sua organização](media/deploying-cvi.png)

### <a name="plan"></a>Plano

Durante a fase de plano, você deve identificar os dispositivos que não substituirá por um dispositivo de equipes nativa e encontrar um parceiro de interoperabilidade de vídeo em nuvem que pode dar suporte a esses dispositivos.  

Também é importante compreender que você precisará de uma licença para cada usuário que agendará reuniões em que você deseja que um dispositivo habilitado para interoperabilidade de vídeo em nuvem ingresse. Observe que os requisitos de licenciamento exatos podem ser obtidos com o parceiro de interoperabilidade de vídeo em nuvem. Certifique-se de que esteja claro antes de iniciar a implantação.

### <a name="configure"></a>Configuração

O parceiro escolhido para a sua implantação do CVI fornecerá um documento de implantação completo que consiste em todas as etapas necessárias para implantar com êxito em sua organização. Isso inclui portas de firewall e intervalos de IP, alterações de configuração para seus dispositivos e outras configurações que precisam ser alteradas.

### <a name="provision"></a>Configura  

Durante a fase de provisionamento, você atribuirá licenças aos usuários adequados de acordo com o guia de configuração do parceiro. Você também precisará passar pelo processo de consentimento do Azure para fornecer ao parceiro acesso ao seu ambiente de equipe. Consulte [permissões e consentimento no ponto de extremidade da plataforma de identidade da Microsoft](https://docs.microsoft.com/azure/active-directory/develop/v2-permissions-and-consent) para obter mais informações sobre o processo de consentimento do Azure.

### <a name="schedule"></a>Prazo

Depois que um usuário estiver habilitado para interoperabilidade de vídeo em nuvem, qualquer reunião agendada usando o suplemento de reunião do teams para Outlook ou o cliente do teams terá as informações adicionais adequadas adicionadas automaticamente à reunião do teams para que os dispositivos compatíveis com a interoperabilidade de vídeo em nuvem possam participar dessas reuniões.

### <a name="join"></a>Ingressar

Dependendo da solução de parceiros, há várias maneiras de ingressar em uma reunião habilitada para interoperabilidade com o vídeo em nuvem. Os cenários de junção de reunião exata serão fornecidos pelo seu parceiro de interoperabilidade de vídeo em nuvem. Listamos alguns exemplos abaixo:

- IVR (resposta de voz interativa) 
  - Você pode discar para o IVR do parceiro usando o tenantkey@domain.
  - Quando estiver no IVR do parceiro, você será solicitado a inserir o VTC conferenceid, que o conectará à reunião do teams.
- Discagem direta 
  - Você pode discar diretamente para a reunião do teams sem interagir com o IVR do parceiro usando o recurso de discagem direta, usando a cadeia de caracteres completa do tenantkey. VTC ConferenceId@domain.
- Discagem com um toque 
  - Se você tiver uma sala de equipes integrada, poderá usar os recursos de discagem com um toque oferecidos pelo seu parceiro (sem precisar digitar qualquer cadeia de caracteres de discagem).

## <a name="manage-cloud-video-interop"></a>Gerenciar a interoperabilidade de vídeo em nuvem

Depois que a interoperabilidade de vídeo em nuvem é implantada, você pode gerenciar os dispositivos usando as soluções fornecidas por nossos parceiros. Cada parceiro lhe fornecerá uma interface administrativa que incluirá licença e gerenciamento de dispositivo. 

O relatório também está disponível diretamente na interface administrativa do parceiro. Para obter mais informações sobre recursos de relatórios, entre em contato com o parceiro de sua escolha. 

### <a name="troubleshooting-cloud-video-interop"></a>Solução de problemas de interoperabilidade de vídeo em nuvem

A interoperabilidade de vídeo em nuvem é um serviço fornecido pelo parceiro. Se você estiver enfrentando problemas, a primeira etapa é conectar um dispositivo que tenha o cliente do teams instalado e conectá-lo ao mesmo segmento do dispositivo de interoperabilidade de vídeo em nuvem que está causando problemas. 

Se o Microsoft Teams funcionar corretamente nesse segmento, e você também tiver seguido todas as diretrizes de rede e configuração que o parceiro forneceu, será necessário entrar em contato com o parceiro para obter mais soluções de problemas. 

## <a name="powershell-for-cloud-video-interop"></a>PowerShell para interoperabilidade de vídeo em nuvem

Os cmdlets do PowerShell a seguir estão disponíveis para você (parcialmente) automatizar a implantação de interoperabilidade de vídeo em nuvem.

- **Get-CsTeamsVideoInteropServicepolicy: a**Microsoft fornece políticas pré-projetadas para cada um dos nossos parceiros compatíveis que permitem que você projete quais parceiros usar para interoperabilidade de vídeo em nuvem.<br>Esse cmdlet permite identificar as políticas pré-projetadas que você pode usar em sua organização. Você pode atribuir essa política a um ou mais dos seus usuários aproveitando o cmdlet Grant-CsTeamsVideoInteropServicePolicy.
- **Grant-CsTeamsVideoInteropServicePolicy**: Este cmdlet permite atribuir uma política pré-projetada para usar em sua organização ou atribuir a política a usuários específicos.
- **New-CsVideoInteropServiceProvider**: Use esse cmdlet para especificar informações sobre um parceiro compatível do CVI que a sua organização gostaria de usar.
- **Set-CsVideoInteropServiceProvider**: Use esse cmdlet para atualizar informações sobre um parceiro de CVI com suporte usado por sua organização.
- **Get-CsVideoInteropServiceProvider**: Use esse cmdlet para obter todos os provedores que foram configurados para uso dentro da organização.
- **Remove-CsVideoInteropServiceProvider**: Use esse cmdlet para remover todas as informações do provedor sobre um provedor que a sua organização não usa mais.
