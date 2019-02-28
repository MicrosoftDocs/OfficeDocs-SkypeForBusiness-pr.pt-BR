---
title: Interoperabilidade de vídeo na nuvem para o Microsoft Teams
author: lolaj
ms.author: lolaj
manager: serdars
ms.topic: article
ms.service: msteams
search.appverid: MET150
ms.reviewer: srividhc
description: Interoperabilidade de vídeo de nuvem de terceiros permite que os dispositivos de sala para ingressar em reuniões do Microsoft Teams da reunião.
localization_priority: Normal
MS.collection: Strat_MT_TeamsAdmin
appliesto:
- Microsoft Teams
ms.openlocfilehash: 7ebf153def5c53f2cabdf9a6293ed55e69c1c2f9
ms.sourcegitcommit: ea1085228894ae448f575f9e13a9f25a1f47e636
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/27/2019
ms.locfileid: "30312264"
---
# <a name="cloud-video-interop-for-microsoft-teams"></a>Interoperabilidade de vídeo na nuvem para o Microsoft Teams

Interoperabilidade de vídeo (CVI) de nuvem é uma solução de terceiros Qualified Microsoft que permite que as salas de reunião de terceiros (telepresença) e os dispositivos de vídeos pessoais (VTCs) para participar de reuniões Teams da Microsoft.
 
Com Teams da Microsoft, você obtém colaboração avançada de conteúdo online em reuniões que incluam compartilhamento de áudio, vídeo e conteúdo. Isso pode ser aproveitado por meio do cliente de desktop e web, bem como por meio de vários dispositivos de parceiro que se integram nativamente Teams da Microsoft. No entanto, muitos clientes já têm investido em teleconferência de vídeo e dispositivos de comunicação de vídeo pessoais, que podem ser caros atualizar. Interoperabilidade de vídeo de nuvem fornece uma solução de fácil, permitindo que você mantenha usando suas soluções existentes até que você está pronto para atualizar.

Com a nuvem interoperabilidade de vídeo, o Teams Microsoft proporciona uma experiência de reunião nativo para todos os participantes – em salas de reunião ou dentro de clientes de equipes.

### <a name="is-cloud-video-interop-for-me"></a>É a interoperabilidade de vídeo de nuvem por mim?

Interoperabilidade de vídeo de nuvem fornece um serviço intermediário enquanto você fazer a transição para uma solução de equipes Microsoft nativo completo, usando os pontos de extremidade de equipes. O serviço fornecido deve ser parte do seu caminho de migração.

Interoperabilidade de vídeo de nuvem destina-se a clientes que atendam aos seguintes critérios:

- Ter uma grande implantação de dispositivos para salas de reunião e a implantação de dispositivos de vídeo pessoais (50 + dispositivos) que não estão qualificados para integração direta com o Microsoft Teams
- São compatíveis com um de nossos parceiros de interoperabilidade de vídeo de nuvem
- Deseja reter o valor de seus investimentos em seus atuais dispositivos de vídeos pessoais e dispositivos de sala de reunião durante a migração para uma solução Microsoft Teams nativo

Enquanto a interoperabilidade de vídeo de nuvem oferece uma ótima solução intermediária, recomendamos que nossos clientes para procurar em nossas soluções de reunião de equipes nativas, como sistemas de sala de equipes, a longo prazo. 

### <a name="partners-certified-for-microsoft-teams"></a>Parceiros certificados para equipes da Microsoft

Os seguintes parceiros têm soluções de interoperabilidade de vídeo for Microsoft Teams. Sua empresa pode escolher funcionar com qualquer combinação desses parceiros dentro de sua empresa. 

|Parceiro|Solução de parceiro|
|----|---|
|![Polycom RealConnect](media/polycom.png) | <a href="https://aka.ms/PolycomRealConnect" target="_blank">Serviço de RealConnect Polycom</a> |
|![Pexip infinito](media/pexip.png)| <a href="https://aka.ms/PexipInfinity" target="_blank">Pexip infinito para equipes da Microsoft</a> | 
|![Gateway blueJeans](media/bluejeans.png)| <a href="https://aka.ms/BluejeansGateway" target="_blank">Gateway blueJeans para equipes da Microsoft</a> |

### <a name="cloud-video-interop-overview"></a>Visão geral de interoperabilidade de vídeo de nuvem

Interoperabilidade de vídeo de nuvem é um serviço de terceiros que é oferecido pelo nossos parceiros para fornecer a interoperabilidade entre soluções de pessoal de dispositivo de vídeo e videoconferência existente no local e Teams da Microsoft.

As soluções oferecidas por nossos parceiros consistem em componentes que podem ser implantados em totalmente nuvem com base ou parcialmente/totalmente no local. 
     
O diagrama a seguir mostra a arquitetura de alto nível dos nossos parceiros de soluções.

![Solução de parceiro de interoperabilidade de vídeo de nuvem de equipes](media/teams-cloud-video-interop-partner-solution.png)


## <a name="deploy-cloud-video-interop"></a>Implantar a interoperabilidade de vídeo de nuvem

Ao implantar uma solução de interoperabilidade de vídeo de nuvem, é importante entender o que você estiver implantando uma solução de parceiro. As etapas gerais que deve ser adotada para implantar a interoperabilidade de vídeo de nuvem são listadas no diagrama a seguir.

![Implantando CVI na sua organização](media/deploying-cvi.png)

### <a name="plan"></a>Planejamento

Durante a fase de planejamento, você deve identificar os dispositivos que você não substituirá com um dispositivo de equipes nativo e encontre um parceiro de interoperabilidade de vídeo de nuvem que pode suportar esses dispositivos.  

Também é importante compreender o que você precisará uma licença de cada usuário que irá agendar reuniões em que você deseja que um dispositivo habilitado para nuvem interoperabilidade de vídeo para ingressar. Observe que os requisitos de licenciamento exatos podem ser obtidos do parceiro de interoperabilidade de vídeo de nuvem. Certifique-se de que esse é criptografado antes de iniciar sua implantação.

### <a name="configure"></a>Configurar

O parceiro que você escolheu para sua implantação CVI fornecerá um documento de implantação completa que consiste em todas as etapas necessárias para implantar com êxito dentro da sua organização. Isso inclui a portas de firewall e intervalos IP, alterações de configuração para seus dispositivos e outras configurações que precisam alterar.

### <a name="provision"></a>Provisão  

Durante a fase de provisão, você irá atribuir licenças para os usuários apropriados de acordo com o parceiro guia de configuração. Você também precisará percorrer o processo de consentimento do Windows Azure para fornecer o acesso do parceiro ao seu ambiente de equipes. Para obter mais informações sobre o processo de consentimento do Azure podem ser encontradas aqui:https://docs.microsoft.com/en-us/azure/active-directory/develop/v2-permissions-and-consent 

### <a name="schedule"></a>Agenda

Depois que um usuário está habilitado para nuvem interoperabilidade de vídeo, qualquer reunião agendada com qualquer reunião equipes suplemento para Outlook ou o cliente de equipes terá as informações apropriadas de adicionais são adicionadas automaticamente para as equipes de reunião isso se o vídeo nuvem Dispositivos compatíveis com o Interop podem ingressar dessas reuniões.

### <a name="join"></a>Ingressar

Dependendo da solução de parceiro, há várias maneiras de ingressar em uma reunião habilitado para nuvem interoperabilidade de vídeo. Exata cenários serão fornecidos pelo seu parceiro de interoperabilidade de vídeo de nuvem de participação da reunião. Apresentaremos alguns exemplos a seguir:

- IVR (resposta interativa de voz) 
  - Você pode discar para IVR do parceiro usando o tenantkey@domain.
  - Quando você estiver no parceiro de IVR, você será solicitado para inserir o conferenceId VTC, que, em seguida, o conectará à reunião equipes.
- Discagem direta 
  - Você pode diretamente discar para a reunião de equipes sem interação com IVR do parceiro usando o recurso de discagem direta interna, usando a cadeia completa de tenantkey. VTC ConferenceId@domain.
- Discagem de um toque 
  - Se você tiver uma sala de equipes integrada, você pode usar os recursos de discagem de um toque oferecidos pelo seu parceiro (sem precisar digitar qualquer cadeia de caracteres de discagem).

## <a name="manage-cloud-video-interop"></a>Gerenciar a interoperabilidade de vídeo de nuvem

Depois de interoperabilidade de vídeo de nuvem for implantada, você pode gerenciar os dispositivos usando o soluções fornecido pelo nossos parceiros. Cada parceiro fornecerá a você uma interface administrativa que incluirá o gerenciamento de licença e dispositivos. 

Relatórios também estão disponível diretamente da interface administrativa do parceiro. Para obter mais informações sobre recursos de relatório, contate o parceiro de sua escolha. 

### <a name="troubleshooting-cloud-video-interop"></a>Solucionando problemas de interoperabilidade de vídeo de nuvem

Interoperabilidade de vídeo de nuvem é um serviço de parceiro fornecida. Se você estiver enfrentando problemas, a primeira etapa é conectar um dispositivo que tenha o cliente de equipes instalado e conectá-la ao mesmo segmento que o dispositivo de interoperabilidade de vídeo de nuvem que está causando problemas. 

Se as funções de equipes corretamente nesse segmento e você também seguiu todas as diretrizes de rede e configuração que forneceu o parceiro, você precisará contatar o parceiro para investigar. 

## <a name="powershell-for-cloud-video-interop"></a>PowerShell para interoperabilidade de vídeo de nuvem

Os seguintes cmdlets do PowerShell estão disponíveis para você (parcialmente) automatizar a implantação de interoperabilidade de vídeo de nuvem.

- **Get-CsTeamsVideoInteropServicepolicy**: a Microsoft fornece diretivas previamente construídas para cada um de nossos parceiros com suporte que permitem que você designar quais parceiros a ser usado para a interoperabilidade de vídeo de nuvem.<br>Este cmdlet permite que você identifique as políticas de pré-construídas que você pode usar em sua organização. Você pode atribuir essa política a um ou mais dos seus usuários utilizando o cmdlet Grant-CsTeamsVideoInteropServicePolicy.
- **Grant-CsTeamsVideoInteropServicePolicy**: este cmdlet permite que você atribuir uma política de pré-construída para uso na sua organização ou atribuir a política a usuários específicos.
- **New-CsVideoInteropServiceProvider**: Use este cmdlet para especificar informações sobre um parceiro CVI com suporte que sua organização gostaria de usar.
- **Set-CsVideoInteropServiceProvider**: Use este cmdlet para atualizar as informações sobre um parceiro CVI com suporte que sua organização usa.
- **Get-CsVideoInteropServiceProvider**: Use este cmdlet para obter todos os provedores que tiverem sido configurados para uso na organização.
- **Remove-CsVideoInteropServiceProvider**: Use este cmdlet para remover todas as informações do provedor sobre um provedor de sua organização não os utiliza mais.
