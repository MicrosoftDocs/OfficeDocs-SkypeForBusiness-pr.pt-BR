---
title: Configurar a interoperabilidade de vídeo na nuvem para o Microsoft Teams
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
search.appverid: MET150
ms.reviewer: srividhc
description: Este artigo explica como você pode planejar e configurar a interoperabilidade de vídeo em nuvem para os usuários da sua organização.
localization_priority: Normal
ms.collection:
- Teams_ITAdmin_Help
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: e91b0e25a7844634577083b26d74a48c788bc45b
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/07/2019
ms.locfileid: "36237047"
---
# <a name="set-up-cloud-video-interop-for-microsoft-teams"></a>Configurar a interoperabilidade de vídeo na nuvem para o Microsoft Teams

Depois de [escolher os parceiros de interoperabilidade de vídeo em nuvem](cloud-video-interop.md), você precisará planejar a implantação, configurar os detalhes de provisionamento e a chave do locatário do parceiro e consentir o aplicativo de interoperabilidade de vídeo em sua organização. O diagrama a seguir descreve o processo. 

![Implantando o CVI em sua organização](media/deploying-cvi.png)

## <a name="plan"></a>Plano

Consulte [interoperabilidade de vídeo em nuvem para Microsoft Teams](cloud-video-interop.md) para obter informações sobre como identificar um parceiro ou parceiros a serem usados em sua organização. 

Para planejar a habilitação de usuário/corrente/em toda a instalação: 

- Escolha um modelo de implantação/modelo hospedado para seu uso
- Selecione o plano de licença ideal para a sua organização. 
- Plano para a capacidade de VMs é a infraestrutura de vídeo que você hospeda.

## <a name="configure"></a>Configuração 

Para configurar a interoperabilidade de vídeo em nuvem, siga estas etapas. 

1. Obter informações de configuração do parceiro/parceiros que você escolheu (chave locatário, appIds...). Você pode usar um ou mais parceiros de interoperabilidade de vídeo em sua organização 

2. Verifique se a sua rede está configurada corretamente. Configure o seu firewall de vídeo baseado em padrões para a passagem de rede de perímetro para dar suporte. Por exemplo: 
    - Cisco VCS-e                  
    - Polycom RPAD

3. Configurar salas integradas com o Exchange e o OTD. Na maioria dos casos, a retransmissão adicional precisa ser configurada e configurada no seu ambiente.


## <a name="provision"></a>Configura
 
A chave do locatário será a discagem para o serviço do parceiro. No exemplo a seguir, 813878896@t.plcm.vc é a chave do locatário. 

![Exemplo de chave de locatário](media/tenant-key-example.png) 

Você precisará executar os seguintes cmdlets para provisionar a chave de locatário e também habilitar os usuários selecionados ou toda a organização para criar reuniões com coordenadas de interoperabilidade de vídeo.

 
- ** [Get-CsTeamsVideoInteropServicepolicy](https://docs.microsoft.com/powershell/module/skype/get-csteamsvideointeropservicepolicy):** A Microsoft fornece políticas pré-projetadas para cada um dos nossos parceiros compatíveis, que permitem que você projete quais parceiros usar para interoperabilidade de vídeo em nuvem.

    Esse cmdlet permite identificar as políticas pré-projetadas que você pode usar em sua organização. Você pode atribuir essa política a um ou mais usuários aproveitando o cmdlet Grant-CsTeamsVideoInteropServicePolicy.
 
- ** [Grant-CsTeamsVideoInteropServicePolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamsvideointeropservicepolicy):** O cmdlet Grant-CsTeamsVideoInteropServicePolicy permite atribuir uma política pré-projetada para usar em sua organização ou atribuir a política a usuários específicos.
 
- ** [New-CsVideoInteropServiceProvider](https://docs.microsoft.com/powershell/module/skype/new-csvideointeropserviceprovider):** Use o New-CsVideoInteropServiceProvider para especificar informações sobre um parceiro de CVI compatível que a sua organização gostaria de usar.
 
- ** [Set-CsVideoInteropServiceProvider](https://docs.microsoft.com/powershell/module/skype/set-csvideointeropserviceprovider):** Use o set-CsVideoInteropServiceProvider para atualizar as informações sobre um parceiro de CVI compatível que a sua organização usa.
 
- ** [Get-CsVideoInteropServiceProvider](https://docs.microsoft.com/powershell/module/skype/get-csvideointeropserviceprovider):** Obtenha todos os provedores que foram configurados para uso na organização.
 
- ** [Remove-CsVideoInteropServiceProvider](https://docs.microsoft.com/powershell/module/skype/remove-csvideointeropserviceprovider):** Use remove-CsVideoInteropServiceProvider para remover todas as informações do provedor sobre um provedor que a sua organização não usa mais.  
 
## <a name="consent"></a>Prévia

Você precisará fornecer consentimento de permissão para os dispositivos de teleconferência de vídeo (VTCs) para ingressar em reuniões de organizações por meio do serviço de parceiro. Este link de consentimento também será fornecido pelo seu parceiro.  
 
Quando essas etapas são concluídas, os usuários habilitados individualmente por meio do cmdlet Grant acima, ou todos os usuários da organização, se o locatário estiver habilitado, terão coordenadas VTC em todas as reuniões do teams que elas agendam. Qualquer VTC pode participar dessas reuniões por meio dessas coordenadas.


|Nome|Descrição resumida da permissão do aplicativo| Descrição|
|--|--|---|
|Calls. JoinGroupCall. All|Ingressar em chamadas e reuniões em grupo como um aplicativo (visualização)|Permite que o aplicativo ingresse em chamadas em grupo e reuniões agendadas em sua organização, sem um usuário conectado.  O aplicativo será incluído nos privilégios de um usuário de diretório para reuniões em seu locatário.|
|Calls. JoinGroupCallasGuest. All|Ingressar em chamadas e reuniões em grupo como usuário convidado (visualização)|Permite que o aplicativo ingresse anonimamente em chamadas de grupo e reuniões agendadas em sua organização, sem um usuário conectado.  O aplicativo será associado como convidado a reuniões em seu locatário.|
|Calls. AccessMedia. All|Acessar fluxos de mídia em uma chamada como um aplicativo (visualização)|Permite que o aplicativo obtenha acesso direto a fluxos de mídia em uma chamada, sem um usuário conectado.|
|OnlineMeetings. Read. All|Ler detalhes da reunião online (visualização)|Permite que o aplicativo Leia detalhes da reunião online em sua organização, sem um usuário conectado.|

## <a name="schedule"></a>Prazo

Em seguida, Agende a reunião do teams com coordenadas de interoperabilidade de vídeo. O usuário habilitado pode agendar reuniões do teams por meio de:
- [Suplemento de reunião do teams para Outlook](teams-add-in-for-outlook.md)
- Cliente do teams desktop e celular


## <a name="join"></a>Ingressar

Você pode ingressar em reuniões de equipe com os dispositivos VTC da seguinte maneira:
 
- IVR (resposta de voz interativa)
    - Você pode discar para o IVR do parceiro usando o tenantkey @ domínio. 
    - Quando estiver no IVR do parceiro, você será solicitado a inserir o VTC conferenceid, que o conectará à reunião do teams.
- Discagem direta
    - Você pode discar diretamente para a reunião do teams sem interagir com o IVR do parceiro usando o recurso de discagem direta usando a cadeia de caracteres completa do tenantkey. VTC Conferenceid @ domínio.
- Discagem com um toque
    - Se você tiver uma sala de equipes integrada, poderá usar os recursos de discagem com um toque oferecidos pelo seu parceiro (sem precisar digitar qualquer cadeia de caracteres de discagem).

Por fim, entre em contato com os usuários do teams em suas reuniões usando áudio, vídeo e compartilhamento de conteúdo. 