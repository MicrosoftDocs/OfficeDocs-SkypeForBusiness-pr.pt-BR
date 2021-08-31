---
title: Configurar Audioconferência para Skype for Business
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
ms.localizationpriority: medium
f1.keywords:
- CSH
ms.custom:
- Audio Conferencing
- LIL_Placement
- O365P_DialInConfDesc
description: 'Aprenda a configurar a discagem ou a conferência de áudio para as pessoas da sua empresa que precisam usar um telefone para participar de chamadas em conferência. '
ms.openlocfilehash: d38adf5e1f5d363cb04aa9eb43109ca2ed394a65
ms.sourcegitcommit: 15e90083c47eb5bcb03ca80c2e83feffe67646f2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/30/2021
ms.locfileid: "58725970"
---
# <a name="set-up-audio-conferencing-for-skype-for-business"></a>Configurar Audioconferência para Skype for Business

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]

Às vezes, as pessoas da sua organização precisam usar um telefone para ligar para uma reunião. Skype for Business inclui o recurso de audioconferência para apenas esta situação! As pessoas podem ligar para Skype for Business reuniões usando um telefone, em vez de usar o aplicativo Skype for Business em um dispositivo móvel ou computador. 
  
Basta configurar uma audioconferência para as pessoas que planejam agendar ou conduzir reuniões. Os participantes da reunião não precisam de nenhuma licença atribuída ou configuração adicional.
  
Para as perguntas frequentes sobre Audioconferência, consulte [Perguntas comuns sobre Audioconferência](/MicrosoftTeams/audio-conferencing-common-questions).

## <a name="step-1-find-out-if-audio-conferencing-is-available-in-your-countryregion"></a>Etapa 1: Descobrir se a audioconferência está disponível em seu país/região
<a name="__top"> </a>

Acesse [Disponibilidade do país e região para audioconferência e planos de chamada](/microsoftteams/country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans) e selecione seu país ou região para obter informações de disponibilidade sobre a audioconferência, assim como informações sobre as sistema telefônico, planos de chamada, números de chamada tarifada e chamada gratuita, e créditos de comunicação. 
 
## <a name="step-2-get-and-assign-licenses"></a>Etapa 2: Comprar e atribuir licenças
 
1. Para caudioonferências, você precisa de uma licença de cada usuário que irá configurar as reuniões discadas. Para saber quais licenças você precisa comprar para Audioconferência e quanto elas custarão, consulte [Skype for Business licenciamento de complemento.](../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md)

    >[!NOTE] 
    > A audioconferência está incluída nas licenças do Office 365 Enterprise E5 e como um complemento.
        
2. Depois de comprar as licenças da audioconferência, você precisará atribuí-las àquelas pessoas na sua organização que irão agendar ou liderar reuniões. Consulte [Atribuir ou remover licenças](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc) para Microsoft 365 Apps para Pequenos e Médios negócios que você comprou para as pessoas em sua organização que vão agendar ou conduzir reuniões.
    
3. Também é recomendável que você atribua licenças créditos de comunicação (são gratuitas) para as mesmas pessoas a quem você atribuiu as licenças na etapa anterior. Para saber como configurar os créditos de comunicação, consulte [Configurar créditos de comunicação para sua organização](/microsoftteams/set-up-communications-credits-for-your-organization).
    
> [!NOTE]
> Você também pode configurar a [Audioconferencia paga por minuto](/microsoftteams/audio-conferencing-pay-per-minute)

## <a name="step-3-get-service-numbers-for-your-conferencing-bridges"></a>Etapa 3: Obtenha números de serviço para suas pontes de conferência
<a name="__top"> </a>

Para audioconferências, você não pode usar números de telefone para usuários; será preciso obter os números de serviço. Você pode obter números de serviço tarifado ou gratuito para suas pontes de conferência. Há três maneiras de obter números de serviço tarifado ou gratuito: 
  
- **Use o Skype for Business de administração.** Para alguns países/regiões, você pode obter números de serviço para suas pontes de conferência usando o Skype for Business de administração. Consulte [Obter números dos telefones de serviço](/microsoftteams/getting-service-phone-numbers).
    
- **Portar seus números de serviço existentes**. Para porta ou transferir números existentes de seu provedor de serviços ou operadora de telefonia atual para Microsoft 365 ou Office 365. Você pode consultar [Transferir os números dos telefones ao Teams](/microsoftteams/phone-number-calling-plans/transfer-phone-numbers-to-teams) ou [Gerenciar números de telefone da sua organização](/microsoftteams/manage-phone-numbers-for-your-organization) para obter mais informações para ajudá-lo.  
  
- **Use um formulário de solicitação para novos números**. Às vezes (dependendo do seu país/região), você não poderá obter seus novos números de serviço usando o centro de administração do Skype for Business ou precisará de números de telefone ou códigos de área específicos. Nesse caso, você precisará fazer o download de um formulário e enviá-lo de volta para nós. Para obter mais informações, consulte [Gerenciar números de telefone para sua organização](/microsoftteams/manage-phone-numbers-for-your-organization). 
    
## <a name="step-4-assign-a-service-number-to-the-conferencing-bridge"></a>Etapa 4: Atribuir um número de serviço para a ponte de conferência
<a name="__top"> </a>

Depois de obter seus números de telefone interurbano e/ou gratuito da sua ponte de conferência, você precisa atribuir os números para que possam ser usados nos convites das reuniões.  

Para atribuir um novo número de telefone para sua ponte de audioconferência:

![Um ícone mostrando o logotipo Skype for Business.](../images/sfb-logo-30x30.png) **Usando o Skype for Business de administração:**

 1. Vá ao **Centro de administração do Microsoft 365** > **Centros de administração** > **Teams** > **Portal herdado**.
 2. Clique em **Voz** > **Números de telefone**.
 3. Clique no número de telefone e clique em **Atribuir**.

Para obter mais detalhes, consulte [Alterar os números de telefone em sua ponte de audioconferência](/MicrosoftTeams/change-the-phone-numbers-on-your-audio-conferencing-bridge).

## <a name="step-5-set-the-default-and-alternate-languages-for-a-conferencing-bridge"></a>Etapa 5: Definir o padrão e os idiomas alternativos para uma ponte de conferência
<a name="__top"> </a>

Em seguida, você deseja definir idiomas de atendimento automático para [Audioconferência](../audio-conferencing-in-office-365/set-auto-attendant-languages-for-audio-conferencing.md) que o atendimento automático de conferência usa para saudar os chamadores quando eles discam para um número de telefone para Audioconferência. 

![Um ícone mostrando o logotipo Microsoft Teams.](../images/teams-logo-30x30.png) **Usando o Microsoft Teams de administração**:

1. No painel, vá para as **Pontes de conferência do** > **Meetings**.
2. Clique no número do telefone da ponte de conferência, clique em **Editar** e escolha o idioma padrão.

![Um ícone mostrando o logotipo Skype for Business.](../images/sfb-logo-30x30.png) **Usando o Skype for Business de administração**:

1. Vá para o centro de administração > **centros de administração**  >  **Teams**  >  **portal herdado.**
2. Selecione **Audioconferência**  >  **ponte microsoft**. 
3. Selecione o número de telefone da ponte de conferência, selecione **Definir idiomas** e escolha o idioma padrão.

## <a name="step-6-set-your-conferencing-bridge-settings"></a>Etapa 6: Definir suas configurações da ponte de conferência
<a name="__top"> </a>
    
Após configurar sua ponte de conferência, verifique se as configurações padrão, como notificações de entrada/saída e o comprimento do PIN, são aquelas que deseja usar; caso contrário, você pode alterá-las. 

![Um ícone mostrando o logotipo Microsoft Teams.](../images/teams-logo-30x30.png) **Usando o Microsoft Teams de administração**:

1. No painel, vá para as **Pontes de conferência do** > **Meetings**.
2. Clique em **Configurações da ponte**. Esse procedimento abrirá o painel **Configurações da ponte**. 

Para mais detalhes, consulte [Alterar as configurações de uma ponte de audioconferência](/MicrosoftTeams/change-the-settings-for-an-audio-conferencing-bridge).

![Um ícone mostrando o logotipo Skype for Business.](../images/sfb-logo-30x30.png) **Usando o Skype for Business de administração:**

1. Vá ao **Centro de administração do Microsoft 365** > **Centros de administração** > **Teams** > **Portal herdado**.
2. Selecione **Configurações de ponte** de  >  **audioconferência da Microsoft**. Esse procedimento abrirá a página de **Configurações da ponte da Microsoft**. 

Para mais detalhes, consulte [Alterar as configurações de uma ponte de audioconferência](/MicrosoftTeams/change-the-settings-for-an-audio-conferencing-bridge).

## <a name="step-7-assign-dial-in-phone-numbers-for-users-who-lead-meetings"></a>Etapa 7: Atribuir números de telefone para discagem para os usuários que realizarão as reuniões

Após ter criado uma ponte de audioconferênci, você precisará definir números de chamada tarifada e chamada gratuita para seus usuários.

Você precisará fazer isso para todas as pessoas na sua organização que irão agendar ou realizar as reuniões. 

![Um ícone mostrando o logotipo Microsoft Teams.](../images/teams-logo-30x30.png) **Usando o Microsoft Teams de administração**:

1. No painel, clique em **Usuários**, clique no usuário da lista e selecione **Editar**.
2. Clique em **Editar** ao lado da **Audioconferência**, e na página da **Audioconferência**, escolha um número nas listas de **Número de interurbano** e **Número gratuito**.

![Um ícone mostrando o logotipo Skype for Business.](../images/sfb-logo-30x30.png) **Usando o Skype for Business de administração:**

1. Vá para o **Centro de administração do Microsoft 365**  >  **Teams**  >  **portal herdado.**
2. Selecione **Usuários de Audioconferência** e selecione o usuário na lista e clique em  >   **Editar**. 

Se você precisar de mais detalhes, consulte [Atribuir a Microsoft como o provedor de serviços de audioconferência](../audio-conferencing-in-office-365/assign-microsoft-as-the-audio-conferencing-provider.md).


## <a name="step-8-set-up-meeting-invitations-optional"></a>Etapa 8: Configurar os convites para reuniões (opcional)
<a name="__top"> </a>
 
Os números de discagem definidos para o usuário serão adicionados automaticamente aos convites da reunião enviados aos participantes da reunião. No entanto, você pode adicionar seus próprios links jurídico, uma mensagem de texto e um pequeno gráfico da empresa. Consulte [Personalizar convites da reunião](../set-up-skype-for-business-online/customize-meeting-invitations.md)
   
## <a name="related-topics"></a>Tópicos relacionados

[Perguntas comuns sobre a Audioconferência](/MicrosoftTeams/audio-conferencing-common-questions)
  
[Instalar o Skype for Business Online](../set-up-skype-for-business-online/set-up-skype-for-business-online.md)
  
[Números de telefone para audioconferência](phone-numbers-for-audio-conferencing.md)
  
[Definir opções para reuniões online e chamadas em conferência](https://support.office.com/article/DCD1CA39-0C1F-466C-9573-F04138FEF5E2)
