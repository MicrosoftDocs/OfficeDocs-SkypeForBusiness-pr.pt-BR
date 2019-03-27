---
title: Configurar a conferência de áudio para Skype para negócios
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: d01954f1-4f37-4cf5-a636-20039e5c59e9
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection:
- Adm_Skype4B_Online
- Strat_SB_PSTN
ms.audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1keywords:
- O365P_DialInConfDesc
ms.custom:
- Audio Conferencing
- LIL_Placement
description: 'Aprenda a configurar dial-in ou conferência de áudio para as pessoas na sua empresa que precisam usar um telefone para ingressar em chamadas de conferência. '
ms.openlocfilehash: d57eedec13d9bd1c01ec9365fd42c0a4dfdc2d96
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/27/2019
ms.locfileid: "30877186"
---
# <a name="set-up-audio-conferencing-for-skype-for-business"></a>Configurar a conferência de áudio para Skype para negócios

Em alguns casos, as pessoas na sua organização precisará usar um telefone para efetuar uma chamada para uma reunião. Skype para negócios inclui o recurso de conferência de áudio para apenas essa situação! As pessoas podem ligar para Skype para reuniões de negócios usando um telefone, em vez de usar o Skype para aplicativo de negócios em um PC ou dispositivo móvel. 
  
You only need to set up Audio Conferencing for people who plan to schedule or lead meetings. Meeting attendees who dial in don't need any licenses assigned to them or other setup.
  
Para as perguntas frequentes sobre Audioconferência, consulte [Perguntas comuns sobre Audioconferência](/MicrosoftTeams/audio-conferencing-common-questions).

## <a name="step-1-find-out-if-audio-conferencing-is-available-in-your-countryregion"></a>Etapa 1: Descobrir se a audioconferência está disponível em seu país/região
<a name="__top"> </a>

Acesse [Disponibilidade do país e região para audioconferência e planos de chamada](/microsoftteams/country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans) e selecione seu país ou região para obter informações de disponibilidade sobre a audioconferência, assim como informações sobre as sistema telefônico, planos de chamada, números de chamada tarifada e chamada gratuita, e créditos de comunicação. 
 
## <a name="step-2-get-and-assign-licenses"></a>Etapa 2: Comprar e atribuir licenças
 
1. Para caudioonferências, você precisa de uma licença de cada usuário que irá configurar as reuniões discadas. Para saber quais licenças você precisará comprar para conferência de áudio e quanto eles terá um custo, consulte [Skype para licenciamento de complemento de negócios](../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md).

    >[!NOTE] 
    > Serviços de audioconferência é incluído no Office 365 Enterprise E5 licenças e como um complemento.
        
2. Depois que você adquire as licenças de conferência de áudio, você precisará atribuí-las às pessoas em sua organização que estão indo para agendar ou liderança de reuniões. Consulte [atribuir ou remover licenças do Office 365 for business](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc) você comprou às pessoas em sua organização que pretende agendar ou líder de reuniões.
    
3. Também é recomendável que você atribua licenças créditos de comunicação (são gratuitas) para as mesmas pessoas a quem você atribuiu as licenças na etapa anterior. Para saber como configurar os créditos de comunicação, consulte [Configurar créditos de comunicação para sua organização](/microsoftteams/set-up-communications-credits-for-your-organization).
    
> [!NOTE]
> Você também pode configurar a [Conferência de áudio de pagamento por minuto](/microsoftteams/audio-conferencing-pay-per-minute).

## <a name="step-3-get-service-numbers-for-your-conferencing-bridges"></a>Etapa 3: Obtenha números de serviço para suas pontes de conferência
<a name="__top"> </a>

Para audioconferências, você não pode usar números de telefone para usuários; será preciso obter os números de serviço. Você pode obter números de serviço tarifado ou gratuito para suas pontes de conferência. Há três maneiras de obter números de serviço tarifado ou gratuito: 
  
- **Use o Skype para centro de administração de negócios**. Para alguns países/regiões, você pode obter os números de serviço para seus pontes de conferência usando o Skype para o Centro de administração de negócios. Consulte [Getting números de telefone de serviço](../what-is-phone-system-in-office-365/getting-service-phone-numbers.md).
    
- **Porta seus números de serviço existente**. Faça a portabilidade ou transfira os números existentes do seu provedor de serviços ou operadora de telefonia atual para o Office 365. Consulte [Transferir números de telefone para o Office 365](/microsoftteams/transfer-phone-numbers-to-office-365) ou [Gerenciar números de telefone para sua organização](/microsoftteams/manage-phone-numbers-for-your-organization) para obter mais informações sobre esse assunto.  
  
- **Usar um formulário de solicitação para novos números**. Às vezes (dependendo do seu país/região) não será possível obter seus números de serviço nova usando o Skype para o Centro de administração de negócios ou, você precisará de números de telefone específico ou códigos de área. Se for o caso, será necessário baixar um formulário e enviá-lo para nós. Para obter mais informações, consulte [Gerenciar números de telefone para sua organização](/microsoftteams/manage-phone-numbers-for-your-organization). 
    
## <a name="step-4-assign-a-service-number-to-the-conferencing-bridge"></a>Etapa 4: Atribuir um número de serviço para a ponte de conferência
<a name="__top"> </a>

Depois que você obtenha sua chamada Tarifada e/ou números de telefone gratuitos para sua ponte de conferência, você precisa atribuir números para que possam ser usadas em convites de reunião.  

Para atribuir um novo número de telefone para sua ponte de audioconferência:

![logotipo-sfb-30x30.png](../images/sfb-logo-30x30.png) **usando o Skype para o Centro de administração de negócios:**

 1. Vá para o **Centro de administração do Microsoft 365** > **Admin centrais** > **equipes** > **portal herdada**.
 2. Selecione **voz** > **números de telefone**.
 3. Selecione o número de telefone e clique em **atribuir**.

Para obter mais detalhes, consulte [alterar os números de telefone na sua ponte de conferência de áudio](/MicrosoftTeams/change-the-phone-numbers-on-your-audio-conferencing-bridge).

## <a name="step-5-set-the-default-and-alternate-languages-for-a-conferencing-bridge"></a>Etapa 5: Definir o padrão e os idiomas alternativos para uma ponte de conferência
<a name="__top"> </a>

Em seguida, você deseja [definir os idiomas de atendedor automático de conferência de áudio](../audio-conferencing-in-office-365/set-auto-attendant-languages-for-audio-conferencing.md) que o atendedor automático de conferência usa para saudar chamadores quando eles discam para um número de telefone para audioconferências. 

![as equipes de logotipo-30x30.png](../images/teams-logo-30x30.png) **usando o Centro de administração de equipes da Microsoft**:

1. No painel, vá para **reuniões** > **pontes de conferência**.
2. Selecione o número de telefone de ponte de conferência, clique em **Editar**e escolha o idioma padrão.

![logotipo-sfb-30x30.png](../images/sfb-logo-30x30.png) **usando o Skype para centro de administração de negócios**:

1. Vá para o **Centro de administração do Office 365** > **Admin centrais** > **equipes** > **portal herdada**.
2. Selecione **audioconferências** > **ponte da Microsoft**. 
3. Selecione o número de telefone de ponte de conferência, selecione **o conjunto de idiomas**e escolha o idioma padrão.

## <a name="step-6-set-your-conferencing-bridge-settings"></a>Etapa 6: Definir suas configurações da ponte de conferência
<a name="__top"> </a>
    
Após configurar sua ponte de conferência, verifique se as configurações padrão, como notificações de entrada/saída e o comprimento do PIN, são aquelas que deseja usar; caso contrário, você pode alterá-las. 

![as equipes de logotipo-30x30.png](../images/teams-logo-30x30.png) **usando o Centro de administração de equipes da Microsoft**:

1. No painel, vá para **reuniões** > **pontes de conferência**.
2. Selecione **configurações de ponte**. Esse procedimento abrirá o painel **Configurações da ponte**. 

Para mais detalhes, consulte [Alterar as configurações de uma ponte de audioconferência](/MicrosoftTeams/change-the-settings-for-an-audio-conferencing-bridge).

![logotipo-sfb-30x30.png](../images/sfb-logo-30x30.png) **usando o Skype para o Centro de administração de negócios:**

1. Vá para o **Centro de administração do Microsoft 365** > **Admin centrais** > **equipes** > **portal herdada**.
2. Selecione **audioconferências** > **configurações de ponte da Microsoft**. Esse procedimento abrirá a página de **Configurações da ponte da Microsoft**. 

Para mais detalhes, consulte [Alterar as configurações de uma ponte de audioconferência](/MicrosoftTeams/change-the-settings-for-an-audio-conferencing-bridge).

## <a name="step-7-assign-dial-in-phone-numbers-for-users-who-lead-meetings"></a>Etapa 7: Atribuir números de telefone para discagem para os usuários que realizarão as reuniões

Após ter criado uma ponte de audioconferênci, você precisará definir números de chamada tarifada e chamada gratuita para seus usuários.

Você precisará fazer isso para todas as pessoas na sua organização que irão agendar ou realizar as reuniões. 

![as equipes de logotipo-30x30.png](../images/teams-logo-30x30.png) **usando o Centro de administração de equipes da Microsoft**:

1. No painel, clique em **usuários**, selecione o usuário na lista e selecione **Editar**.
2. Selecione **Editar** ao lado de **Conferência de áudio**e, em seguida, no painel de **Conferência de áudio** , escolha um número nas listas de número de **número de Chamada Tarifada** e de **chamada gratuita** .

![logotipo-sfb-30x30.png](../images/sfb-logo-30x30.png) **usando o Skype para o Centro de administração de negócios:**

1. Vá para o **Centro de administração do Microsoft 365** > **equipes** > **portal herdada**.
2. Selecione **audioconferências** > **usuários**e, em seguida, selecione o usuário na lista e clique em **Editar**. 

Se você precisar de mais detalhes, consulte [Atribuir a Microsoft como o provedor de serviços de audioconferência](../audio-conferencing-in-office-365/assign-microsoft-as-the-audio-conferencing-provider.md).


## <a name="step-8-set-up-meeting-invitations-optional"></a>Etapa 8: Configurar os convites para reuniões (opcional)
<a name="__top"> </a>
 
Os números de discagem que são definidos para o usuário serão adicionados automaticamente aos convites de reunião que são enviados para os participantes da reunião. No entanto, você pode adicionar seus próprios links jurídico, uma mensagem de texto e um pequeno gráfico da empresa. Consulte [Personalizar convites de reunião](../set-up-skype-for-business-online/customize-meeting-invitations.md).
   
## <a name="related-topics"></a>Tópicos relacionados

[Perguntas comuns sobre a Audioconferência](/MicrosoftTeams/audio-conferencing-common-questions)
  
[Instalar o Skype for Business Online](../set-up-skype-for-business-online/set-up-skype-for-business-online.md)
  
[Números de telefone para audioconferência](phone-numbers-for-audio-conferencing.md)
  
[Definir opções para reuniões online e chamadas em conferência](https://support.office.com/article/DCD1CA39-0C1F-466C-9573-F04138FEF5E2)
