---
title: Configurar a conferência de áudio para o Microsoft Teams
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
- M365-voice
- M365-collaboration
audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
f1.keywords:
- NOCSH
ms.custom:
- Audio Conferencing
- LIL_Placement
description: 'Saiba como configurar a conferência discada ou de áudio para as pessoas em sua empresa que precisam usar um telefone para participar de chamadas em conferência. '
ms.openlocfilehash: 0a483dba984799a3c9e0f1a63ed908dde9a9ca08
ms.sourcegitcommit: 19f534bfafbc74dbc2d381672b0650a3733cb982
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/03/2020
ms.locfileid: "41693946"
---
# <a name="set-up-audio-conferencing-for-microsoft-teams"></a>Configurar a conferência de áudio para o Microsoft Teams

Às vezes, as pessoas em sua organização precisarão usar um telefone para ligar para uma reunião. O Microsoft Teams inclui o recurso de videoconferência por apenas essa situação! As pessoas podem fazer chamadas para reuniões do teams usando um telefone, em vez de usar o aplicativo Teams em um dispositivo móvel ou computador. 
  
Basta configurar uma Audioconferência para as pessoas que planejam agendar ou liderar reuniões. Os participantes da reunião não precisam de nenhuma licença atribuída ou configuração adicional.
  
Para as perguntas frequentes sobre Audioconferência, consulte [Perguntas comuns sobre Audioconferência](audio-conferencing-common-questions.md).

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]
  
## <a name="step-1-find-out-if-audio-conferencing-is-available-in-your-countryregion"></a>Etapa 1: Descobrir se a audioconferência está disponível em seu país/região
<a name="__top"> </a>

Acesse [Disponibilidade do país e região para audioconferência e planos de chamada](country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md) e selecione seu país ou região para obter informações de disponibilidade sobre a audioconferência, assim como informações sobre as sistema telefônico, planos de chamada, números de chamada tarifada e chamada gratuita, e créditos de comunicação. 
 
## <a name="step-2-get-and-assign-licenses"></a>Etapa 2: Comprar e atribuir licenças
 
1. Para caudioonferências, você precisa de uma licença de cada usuário que irá configurar as reuniões discadas. Para saber quais licenças você precisa comprar para a conferência de áudio e quanto elas custarão, consulte [Licenciamento de Complementos do Microsoft Teams](teams-add-on-licensing/microsoft-teams-add-on-licensing.md).

    >[!NOTE] 
    > A videoconferência está incluída nas licenças do Office 365 Enterprise E5 e como um complemento.
        
2. Depois de comprar as licenças de audioconferência, você precisará atribuí-las a essas pessoas em sua organização que irão agendar ou conduzir reuniões. Confira [atribuir licenças a usuários do Office 365 para empresas](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc) que você comprou para as pessoas em sua organização que devem agendar ou conduzir reuniões.
    
3. Também é recomendável que você atribua licenças créditos de comunicação (são gratuitas) para as mesmas pessoas a quem você atribuiu as licenças na etapa anterior. Para saber como configurar os créditos de comunicação, consulte [Configurar créditos de comunicação para sua organização](set-up-communications-credits-for-your-organization.md).
    
> [!NOTE]
> Você também pode configurar [a conferência de áudio de pagamento por minuto](audio-conferencing-pay-per-minute.md).

## <a name="step-3-get-service-numbers-for-your-conferencing-bridges"></a>Etapa 3: Obtenha números de serviço para suas pontes de conferência
<a name="__top"> </a>

Para audioconferências, você não pode usar números de telefone para usuários; será preciso obter os números de serviço. Você pode obter números de serviço tarifado ou gratuito para suas pontes de conferência. Há três maneiras de obter números de serviço tarifado ou gratuito: 
  
- **Use o centro de administração do Microsoft Teams**. Para alguns países/regiões, você pode obter números de serviço para suas pontes de conferência usando o centro de administração do Microsoft Teams. Veja [obtendo números de telefone de serviço](/microsoftteams/getting-service-phone-numbers).
    
- **Portar seus números de serviço existentes**. Faça a portabilidade ou transfira os números existentes do seu provedor de serviços ou operadora de telefonia atual para o Office 365. Você pode ver [transferir números de telefone para o Teams](phone-number-calling-plans/transfer-phone-numbers-to-teams.md) ou [gerenciar números de telefone de sua organização](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md) para obter mais informações para ajudá-lo a fazer isso.  
  
- **Use um formulário de solicitação para novos números**. Às vezes (dependendo do seu país/região) você não poderá obter seus novos números de serviço usando o centro de administração do Microsoft Teams ou será necessário números de telefone ou códigos de área específicos. Se for o caso, será necessário baixar um formulário e enviá-lo para nós. Para obter mais informações, consulte [Gerenciar números de telefone para sua organização](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md). 
    
## <a name="step-4-assign-a-service-number-to-the-conferencing-bridge"></a>Etapa 4: Atribuir um número de serviço para a ponte de conferência
<a name="__top"> </a>

Depois de obter seus números de telefone de chamada tarifada e/ou de chamada gratuita para a sua ponte de conferência, você precisa atribuir os números para que possam ser usados em convites de reunião.  

Siga estas etapas para atribuir um novo número de telefone à sua ponte de conferência de áudio.

![Um ícone mostrando o logotipo](media/sfb-logo-30x30.png) do Skype for Business **usando o centro de administração do Skype for Business:**

 1. Vá para o**** > **** > **portal herdado**do **Centro** > de administração do Microsoft 365.
 2. Selecione **Voz** > **Números de telefone**.
 3. Selecione o número de telefone e clique em **atribuir**.

Para obter mais detalhes, consulte [alterar os números de telefone na ponte de videoconferência](change-the-phone-numbers-on-your-audio-conferencing-bridge.md).

## <a name="step-5-set-the-default-and-alternate-languages-for-a-conferencing-bridge"></a>Etapa 5: Definir o padrão e os idiomas alternativos para uma ponte de conferência
<a name="__top"></a> Em seguida, você deseja [definir os idiomas do atendedor automático para videoconferências no Microsoft Teams](set-auto-attendant-languages-for-audio-conferencing-in-teams.md) que o atendedor automático da conferência usa para usar os chamadores de saudação quando discar para um número de telefone para conferência de áudio. 

![Um ícone mostrando o logotipo](media/teams-logo-30x30.png) do Microsoft Teams **usando o centro de administração do Microsoft Teams**:

1. No painel, vá para **reuniões** > **conferência pontes**.
2. Selecione o número de telefone da ponte de conferência, clique em **Editar**e escolha o idioma padrão.

## <a name="step-6-set-your-conferencing-bridge-settings"></a>Etapa 6: Definir suas configurações da ponte de conferência
<a name="__top"> </a>
    
Após configurar sua ponte de conferência, verifique se as configurações padrão, como notificações de entrada/saída e o comprimento do PIN, são aquelas que deseja usar; caso contrário, você pode alterá-las. 

![Um ícone mostrando o logotipo](media/teams-logo-30x30.png) do Microsoft Teams **usando o centro de administração do Microsoft Teams**:

1. No painel, vá para **reuniões** > **conferência pontes**.
2. Selecione **configurações de ponte**. Esse procedimento abrirá o painel **Configurações da ponte**. 

Para mais detalhes, consulte [Alterar as configurações de uma ponte de audioconferência](change-the-settings-for-an-audio-conferencing-bridge.md).

## <a name="step-7-assign-dial-in-phone-numbers-for-users-who-lead-meetings"></a>Etapa 7: Atribuir números de telefone para discagem para os usuários que realizarão as reuniões

Após ter criado uma ponte de audioconferênci, você precisará definir números de chamada tarifada e chamada gratuita para seus usuários.

Você precisará fazer isso para todas as pessoas na sua organização que irão agendar ou realizar as reuniões. 

![Um ícone mostrando o logotipo](media/teams-logo-30x30.png) do Microsoft Teams **usando o centro de administração do Microsoft Teams**:

1. No painel, clique em **usuários**, selecione o usuário na lista e selecione **Editar**.
2. Selecione **Editar** ao lado **de videoconferência**e, em seguida, no painel **conferência de áudio** , escolha um número nas listas número de **chamada** e número de **chamada gratuita** .

Se você precisar de mais detalhes, consulte [Atribuir a Microsoft como o provedor de serviços de audioconferência](/skypeforbusiness/audio-conferencing-in-office-365/assign-microsoft-as-the-audio-conferencing-provider).


## <a name="step-8-set-up-meeting-invitations-optional"></a>Etapa 8: Configurar os convites para reuniões (opcional)
<a name="__top"> </a>
 
Os números de discagem definidos para o usuário serão automaticamente adicionados aos convites da reunião que são enviados para os participantes da reunião. No entanto, você pode adicionar seus próprios links jurídico, uma mensagem de texto e um pequeno gráfico da empresa. Veja [personalizar convites de reunião](meeting-settings-in-teams.md#customize-meeting-invitations).
   
## <a name="related-topics"></a>Tópicos relacionados

[Perguntas comuns sobre a Audioconferência](audio-conferencing-common-questions.md)
  
[Números de telefone para audioconferência no Microsoft Teams](phone-numbers-for-audio-conferencing-in-teams.md)
  
[Definir opções para reuniões online e chamadas em conferência](https://support.office.com/article/DCD1CA39-0C1F-466C-9573-F04138FEF5E2)
