---
title: Configurar a conferência de áudio para o Skype for Business
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
audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Audio Conferencing
- LIL_Placement
- O365P_DialInConfDesc
description: 'Aprenda a configurar a discagem ou a conferência de áudio para as pessoas da sua empresa que precisam usar um telefone para participar de chamadas em conferência. '
ms.openlocfilehash: bfd9c9ec31736b0f7fc16f15a907c87406113871
ms.sourcegitcommit: 36f7ec432090683aedb77a5bd7856e1b10af2a81
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/08/2020
ms.locfileid: "44163940"
---
# <a name="set-up-audio-conferencing-for-skype-for-business"></a>Configurar a conferência de áudio para o Skype for Business

Às vezes, as pessoas em sua organização precisarão usar um telefone para ligar para uma reunião. O Skype for Business inclui o recurso de audioconferência por apenas essa situação! As pessoas podem fazer chamadas para reuniões do Skype for Business usando um telefone, em vez de usar o aplicativo Skype for Business em um dispositivo móvel ou computador. 
  
You only need to set up Audio Conferencing for people who plan to schedule or lead meetings. Meeting attendees who dial in don't need any licenses assigned to them or other setup.
  
Para as perguntas frequentes sobre Audioconferência, consulte [Perguntas comuns sobre Audioconferência](/MicrosoftTeams/audio-conferencing-common-questions).

## <a name="step-1-find-out-if-audio-conferencing-is-available-in-your-countryregion"></a>Etapa 1: Descobrir se a audioconferência está disponível em seu país/região
<a name="__top"> </a>

Acesse [Disponibilidade do país e região para audioconferência e planos de chamada](/microsoftteams/country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans) e selecione seu país ou região para obter informações de disponibilidade sobre a audioconferência, assim como informações sobre as sistema telefônico, planos de chamada, números de chamada tarifada e chamada gratuita, e créditos de comunicação. 
 
## <a name="step-2-get-and-assign-licenses"></a>Etapa 2: Comprar e atribuir licenças
 
1. Para videoconferência, você precisa de uma licença para cada usuário que irá configurar reuniões discadas. Para saber quais licenças você precisa comprar para a videoconferência e quanto elas custarão, consulte [Licenciamento de Complementos do Skype for Business](../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md).

    >[!NOTE] 
    > A audioconferência está incluída nas licenças do Office 365 Enterprise E5 e como um complemento.
        
2. Depois de comprar as licenças da audioconferência, você precisará atribuí-las àquelas pessoas na sua organização que irão agendar ou liderar reuniões. Consulte [atribuir ou remover licenças para aplicativos do Microsoft 365 para empresas](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc) que você comprou para as pessoas em sua organização que vão agendar ou conduzir reuniões.
    
3. Também é recomendável que você atribua licenças créditos de comunicação (são gratuitas) para as mesmas pessoas a quem você atribuiu as licenças na etapa anterior. Para saber como configurar os créditos de comunicação, consulte [Configurar créditos de comunicação para sua organização](/microsoftteams/set-up-communications-credits-for-your-organization).
    
> [!NOTE]
> Você também pode configurar a [Audioconferencia paga por minuto](/microsoftteams/audio-conferencing-pay-per-minute)

## <a name="step-3-get-service-numbers-for-your-conferencing-bridges"></a>Etapa 3: Obtenha números de serviço para suas pontes de conferência
<a name="__top"> </a>

Para audioconferências, você não pode usar números de telefone para usuários; será preciso obter os números de serviço. Você pode obter números de serviço tarifado ou gratuito para suas pontes de conferência. Há três maneiras de obter números de serviço tarifado ou gratuito: 
  
- **Use o centro de administração do Skype for Business**. Para alguns países/regiões, você pode obter números de serviço para suas pontes de conferência usando o centro de administração do Skype for Business. Consulte [Obter números dos telefones de serviço](/microsoftteams/getting-service-phone-numbers).
    
- **Portar seus números de serviço existentes**. Para transferir ou transferir números existentes do seu provedor de serviços atual ou da operadora de telefone para o Microsoft 365 ou o Office 365. Você pode consultar [Transferir os números dos telefones ao Teams](/microsoftteams/phone-number-calling-plans/transfer-phone-numbers-to-teams) ou [Gerenciar números de telefone da sua organização](/microsoftteams/manage-phone-numbers-for-your-organization) para obter mais informações para ajudá-lo.  
  
- **Use um formulário de solicitação para novos números**. Às vezes (dependendo do seu país/região) você não poderá obter seus novos números de serviço usando o centro de administração do Skype for Business ou será necessário números de telefone ou códigos de área específicos. Nesse caso, você precisará fazer o download de um formulário e enviá-lo de volta para nós. Para obter mais informações, consulte [Gerenciar números de telefone para sua organização](/microsoftteams/manage-phone-numbers-for-your-organization). 
    
## <a name="step-4-assign-a-service-number-to-the-conferencing-bridge"></a>Etapa 4: Atribuir um número de serviço para a ponte de conferência
<a name="__top"> </a>

Depois de obter seus números de telefone interurbano e/ou gratuito da sua ponte de conferência, você precisa atribuir os números para que possam ser usados nos convites das reuniões.  

Para atribuir um novo número de telefone para sua ponte de audioconferência:

![Um ícone mostrando o logotipo do Skype for Business](../images/sfb-logo-30x30.png) **Usar o centro de administração do Skype for Business:**

 1. Vá ao **Centro de administração do Microsoft 365** > **Centros de administração** > **Teams** > **Portal herdado**.
 2. Clique em **Voz** > **Números de telefone**.
 3. Clique no número de telefone e clique em **Atribuir**.

Para obter mais detalhes, consulte [alterar os números de telefone na ponte de videoconferência](/MicrosoftTeams/change-the-phone-numbers-on-your-audio-conferencing-bridge).

## <a name="step-5-set-the-default-and-alternate-languages-for-a-conferencing-bridge"></a>Etapa 5: Definir o padrão e os idiomas alternativos para uma ponte de conferência
<a name="__top"> </a>

Em seguida, você deseja [definir os idiomas do atendedor automático para a videoconferência](../audio-conferencing-in-office-365/set-auto-attendant-languages-for-audio-conferencing.md) que o atendedor automático da conferência usa para receber chamadas de saudação quando discar para um número de telefone para videoconferências. 

![Um ícone mostrando o logotipo do Microsoft Teams](../images/teams-logo-30x30.png) **Use o centro de administração do Microsoft Teams**:

1. No painel, vá para as **Pontes de conferência do** > **Meetings**.
2. Clique no número do telefone da ponte de conferência, clique em **Editar** e escolha o idioma padrão.

![Um ícone mostrando o logotipo](../images/sfb-logo-30x30.png) do Skype for Business **usando o centro de administração do Skype for Business**:

1. Vá para o centro de administração >**portal**de**equipes** > do centro de **Administração** > .
2. Selecione **áudio videoconferência** > **Microsoft Bridge**. 
3. Selecione o número de telefone da ponte de conferência, selecione **definir idiomas**e, em seguida, escolha o idioma padrão.

## <a name="step-6-set-your-conferencing-bridge-settings"></a>Etapa 6: Definir suas configurações da ponte de conferência
<a name="__top"> </a>
    
Após configurar sua ponte de conferência, verifique se as configurações padrão, como notificações de entrada/saída e o comprimento do PIN, são aquelas que deseja usar; caso contrário, você pode alterá-las. 

![Um ícone mostrando o logotipo do Microsoft Teams](../images/teams-logo-30x30.png) **Use o centro de administração do Microsoft Teams**:

1. No painel, vá para as **Pontes de conferência do** > **Meetings**.
2. Clique em **Configurações da ponte**. Esse procedimento abrirá o painel **Configurações da ponte**. 

Para mais detalhes, consulte [Alterar as configurações de uma ponte de audioconferência](/MicrosoftTeams/change-the-settings-for-an-audio-conferencing-bridge).

![Um ícone mostrando o logotipo do Skype for Business](../images/sfb-logo-30x30.png) **Usar o centro de administração do Skype for Business:**

1. Vá ao **Centro de administração do Microsoft 365** > **Centros de administração** > **Teams** > **Portal herdado**.
2. Selecione **Audio conferencing** > **configurações da Microsoft Bridge**de audioconferência. Esse procedimento abrirá a página de **Configurações da ponte da Microsoft**. 

Para mais detalhes, consulte [Alterar as configurações de uma ponte de audioconferência](/MicrosoftTeams/change-the-settings-for-an-audio-conferencing-bridge).

## <a name="step-7-assign-dial-in-phone-numbers-for-users-who-lead-meetings"></a>Etapa 7: Atribuir números de telefone para discagem para os usuários que realizarão as reuniões

Após ter criado uma ponte de audioconferênci, você precisará definir números de chamada tarifada e chamada gratuita para seus usuários.

Você precisará fazer isso para todas as pessoas na sua organização que irão agendar ou realizar as reuniões. 

![Um ícone mostrando o logotipo do Microsoft Teams](../images/teams-logo-30x30.png) **Use o centro de administração do Microsoft Teams**:

1. No painel, clique em **Usuários**, clique no usuário da lista e selecione **Editar**.
2. Clique em **Editar** ao lado da **Audioconferência**, e na página da **Audioconferência**, escolha um número nas listas de **Número de interurbano** e **Número gratuito**.

![Um ícone mostrando o logotipo do Skype for Business](../images/sfb-logo-30x30.png) **Usar o centro de administração do Skype for Business:**

1. Vá para o**portal herdado** > **Team** >  **Center de administração do Microsoft 365**.
2. Selecione **Audio conferencing** > **usuários**de audioconferência e, em seguida, selecione o usuário na lista e clique em **Editar**. 

Se você precisar de mais detalhes, consulte [Atribuir a Microsoft como o provedor de serviços de audioconferência](../audio-conferencing-in-office-365/assign-microsoft-as-the-audio-conferencing-provider.md).


## <a name="step-8-set-up-meeting-invitations-optional"></a>Etapa 8: Configurar os convites para reuniões (opcional)
<a name="__top"> </a>
 
Os números de discagem definidos para o usuário serão adicionados automaticamente aos convites da reunião enviados aos participantes da reunião. No entanto, você pode adicionar seus próprios links jurídico, uma mensagem de texto e um pequeno gráfico da empresa. Consulte [Personalizar convites da reunião](../set-up-skype-for-business-online/customize-meeting-invitations.md)
   
## <a name="related-topics"></a>Tópicos relacionados

[Perguntas comuns sobre a Audioconferência](/MicrosoftTeams/audio-conferencing-common-questions)
  
[Instalar o Skype for Business Online](../set-up-skype-for-business-online/set-up-skype-for-business-online.md)
  
[Números de telefone para audioconferência](phone-numbers-for-audio-conferencing.md)
  
[Definir opções para reuniões online e chamadas em conferência](https://support.office.com/article/DCD1CA39-0C1F-466C-9573-F04138FEF5E2)
