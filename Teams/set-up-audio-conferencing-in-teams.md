---
title: Configurar a conferência de áudio for Microsoft Teams
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: d01954f1-4f37-4cf5-a636-20039e5c59e9
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- Teams_ITAdmin_Help
- M365-collaboration
ms.audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Audio Conferencing
- LIL_Placement
description: 'Aprenda a configurar dial-in ou conferência de áudio para as pessoas na sua empresa que precisam usar um telefone para ingressar em chamadas de conferência. '
ms.openlocfilehash: c5925677889d9a81e15ccb15494163fd28c14639
ms.sourcegitcommit: bc2b227b4ac0a9521993f808a1361b4f9bc7faad
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/14/2019
ms.locfileid: "30635517"
---
# <a name="set-up-audio-conferencing-for-microsoft-teams"></a>Configurar a conferência de áudio for Microsoft Teams

Em alguns casos, as pessoas na sua organização precisará usar um telefone para efetuar uma chamada para uma reunião. Microsoft Teams inclui o recurso de conferência de áudio para apenas essa situação! As pessoas podem ligar para reuniões de equipes usando um telefone, em vez de usar o aplicativo de equipes em um PC ou dispositivo móvel. 
  
Basta configurar uma Audioconferência para as pessoas que planejam agendar ou liderar reuniões. Os participantes da reunião não precisam de nenhuma licença atribuída ou configuração adicional.
  
Para as perguntas frequentes sobre Audioconferência, consulte [Perguntas comuns sobre Audioconferência](audio-conferencing-common-questions.md).

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]
  
## <a name="step-1-find-out-if-audio-conferencing-is-available-in-your-countryregion"></a>Etapa 1: Descobrir se a audioconferência está disponível em seu país/região
<a name="__top"> </a>

Acesse [Disponibilidade do país e região para audioconferência e planos de chamada](country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md) e selecione seu país ou região para obter informações de disponibilidade sobre a audioconferência, assim como informações sobre as sistema telefônico, planos de chamada, números de chamada tarifada e chamada gratuita, e créditos de comunicação. 
 
## <a name="step-2-get-and-assign-licenses"></a>Etapa 2: Comprar e atribuir licenças
 
1. Para caudioonferências, você precisa de uma licença de cada usuário que irá configurar as reuniões discadas. Para saber quais licenças você precisará comprar para conferência de áudio e quanto eles terá um custo, consulte [Licenciamento de complemento de equipes da Microsoft](teams-add-on-licensing/microsoft-teams-add-on-licensing.md).

    >[!NOTE] 
    > Serviços de audioconferência é incluído no Office 365 Enterprise E5 licenças e como um complemento.
        
2. Depois que você adquire as licenças de audioconferência, é preciso atribuí-las às pessoas em sua organização que irão agendar ou realizar as reuniões. Consulte [Atribuir licenças aos usuários no Office 365 para empresas](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc) , você comprou às pessoas em sua organização que pretende agendar ou líder de reuniões.
    
3. Também é recomendável que você atribua licenças créditos de comunicação (são gratuitas) para as mesmas pessoas a quem você atribuiu as licenças na etapa anterior. Para saber como configurar os créditos de comunicação, consulte [Configurar créditos de comunicação para sua organização](set-up-communications-credits-for-your-organization.md).
    
> [!NOTE]
> Você também pode configurar a [Conferência de áudio de pagamento por minuto](audio-conferencing-pay-per-minute.md).

## <a name="step-3-get-service-numbers-for-your-conferencing-bridges"></a>Etapa 3: Obtenha números de serviço para suas pontes de conferência
<a name="__top"> </a>

Para audioconferências, você não pode usar números de telefone para usuários; será preciso obter os números de serviço. Você pode obter números de serviço tarifado ou gratuito para suas pontes de conferência. Há três maneiras de obter números de serviço tarifado ou gratuito: 
  
- **Usar o Centro de administração de equipes da Microsoft**. Para alguns países/regiões, você pode obter os números de serviço para seus pontes de conferência usando o Centro de administração do Microsoft Teams. Consulte [Getting números de telefone de serviço](https://docs.microsoft.com/SkypeForBusiness/what-is-phone-system-in-office-365/getting-service-phone-numbers?toc=/MicrosoftTeams/toc.json&bc=/microsoftteams/breadcrumb/toc.json).
    
- **Porta seus números de serviço existente**. Faça a portabilidade ou transfira os números existentes do seu provedor de serviços ou operadora de telefonia atual para o Office 365. Consulte [Transferir números de telefone para o Office 365](transfer-phone-numbers-to-office-365.md) ou [Gerenciar números de telefone para sua organização](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md) para obter mais informações sobre esse assunto.  
  
- **Usar um formulário de solicitação para novos números**. Às vezes (dependendo do seu país/região) não será possível obter seus novos números de serviço usando o Centro de administração do Microsoft Teams ou, você precisará de números de telefone específico ou códigos de área. Se for o caso, será necessário baixar um formulário e enviá-lo para nós. Para obter mais informações, consulte [Gerenciar números de telefone para sua organização](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md). 
    
## <a name="step-4-assign-a-service-number-to-the-conferencing-bridge"></a>Etapa 4: Atribuir um número de serviço para a ponte de conferência
<a name="__top"> </a>

Depois que você obtenha sua chamada Tarifada e/ou números de telefone gratuitos para sua ponte de conferência, você precisa atribuir números para que possam ser usadas em convites de reunião.  

Siga essas stesps para atribuir um novo número de telefone para sua ponte de conferência de áudio.

![logotipo-sfb-30x30.png](media/sfb-logo-30x30.png) **usando o Skype para o Centro de administração de negócios:**

 1. Vá para o **Centro de administração do Microsoft 365** > **Admin centrais** > **equipes** > **portal herdada**.
 2. Selecione **voz** > **números de telefone**.
 3. Selecione o número de telefone e clique em **atribuir**.

Para obter mais detalhes, consulte [alterar os números de telefone na sua ponte de conferência de áudio](change-the-phone-numbers-on-your-audio-conferencing-bridge.md).

## <a name="step-5-set-the-default-and-alternate-languages-for-a-conferencing-bridge"></a>Etapa 5: Definir o padrão e os idiomas alternativos para uma ponte de conferência
<a name="__top"></a> Em seguida, você deseja [Definir automática idiomas Atendedor de conferência de áudio em equipes da Microsoft](set-auto-attendant-languages-for-audio-conferencing-in-teams.md) que o atendedor automático de conferência usa para saudar chamadores quando eles discam para um número de telefone para audioconferências. 

![as equipes de logotipo-30x30.png](media/teams-logo-30x30.png) **usando o Centro de administração de equipes da Microsoft**:

1. No painel, vá para **reuniões** > **pontes de conferência**.
2. Selecione o número de telefone de ponte de conferência, clique em **Editar**e escolha o idioma padrão.

## <a name="step-6-set-your-conferencing-bridge-settings"></a>Etapa 6: Definir suas configurações da ponte de conferência
<a name="__top"> </a>
    
Após configurar sua ponte de conferência, verifique se as configurações padrão, como notificações de entrada/saída e o comprimento do PIN, são aquelas que deseja usar; caso contrário, você pode alterá-las. 

![as equipes de logotipo-30x30.png](media/teams-logo-30x30.png) **usando o Centro de administração de equipes da Microsoft**:

1. No painel, vá para **reuniões** > **pontes de conferência**.
2. Selecione **configurações de ponte**. Esse procedimento abrirá o painel **Configurações da ponte**. 

Para mais detalhes, consulte [Alterar as configurações de uma ponte de audioconferência](change-the-settings-for-an-audio-conferencing-bridge.md).

## <a name="step-7-assign-dial-in-phone-numbers-for-users-who-lead-meetings"></a>Etapa 7: Atribuir números de telefone para discagem para os usuários que realizarão as reuniões

Após ter criado uma ponte de audioconferênci, você precisará definir números de chamada tarifada e chamada gratuita para seus usuários.

Você precisará fazer isso para todas as pessoas na sua organização que irão agendar ou realizar as reuniões. 

![as equipes de logotipo-30x30.png](media/teams-logo-30x30.png) **usando o Centro de administração de equipes da Microsoft**:

1. No painel, clique em **usuários**, selecione o usuário na lista e selecione **Editar**.
2. Selecione **Editar** ao lado de **Conferência de áudio**e, em seguida, no painel de **Conferência de áudio** , escolha um número nas listas de número de **número de Chamada Tarifada** e de **chamada gratuita** .

Se você precisar de mais detalhes, consulte [Atribuir a Microsoft como o provedor de serviços de audioconferência](/skypeforbusiness/audio-conferencing-in-office-365/assign-microsoft-as-the-audio-conferencing-provider).


## <a name="step-8-set-up-meeting-invitations-optional"></a>Etapa 8: Configurar os convites para reuniões (opcional)
<a name="__top"> </a>
 
Os números de discagem que são definidos para o usuário serão adicionados automaticamente aos convites de reunião que são enviados para os participantes da reunião. No entanto, você pode adicionar seus próprios links jurídico, uma mensagem de texto e um pequeno gráfico da empresa. Consulte [Personalizar convites de reunião](customize-meeting-invitations.md).
   
## <a name="related-topics"></a>Tópicos relacionados

[Perguntas comuns sobre a Audioconferência](audio-conferencing-common-questions.md)
  
[Números de telefone para audioconferência no Microsoft Teams](phone-numbers-for-audio-conferencing-in-teams.md)
  
[Definir opções para reuniões online e chamadas em conferência](https://support.office.com/article/DCD1CA39-0C1F-466C-9573-F04138FEF5E2)
