---
title: Configurar conferência de áudio para o Skype for Business e Teams da Microsoft
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
- Microsoft Teams
localization_priority: Normal
f1keywords:
- O365P_DialInConfDesc
ms.custom:
- Audio Conferencing
- LIL_Placement
description: 'Saiba como configurar a conferência discada ou áudio para as pessoas em sua empresa que precisam para ingressar em chamadas de conferência usando um telefone. '
ms.openlocfilehash: 3ac6b6dbe562b7aff14394b5dbd2888ce04eb1c7
ms.sourcegitcommit: 940cb253923e3537cb7fb4d7ce875ed9bfbb72db
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/07/2018
ms.locfileid: "23887947"
---
# <a name="set-up-audio-conferencing-for-skype-for-business-and-microsoft-teams"></a>Configurar conferência de áudio para o Skype for Business e Teams da Microsoft

Às vezes, as pessoas em sua organização precisarão usar um telefone para ligar para uma reunião. Skype para Teams da Microsoft e de negócios incluir o recurso de conferência de áudio para apenas essa situação! As pessoas podem ligar para Skype para reuniões de negócios ou Microsoft Teams usando um telefone, em vez de usar o Skype para negócios ou Teams Microsoft app em um PC ou dispositivo móvel. 
  
Você precisa configurar a conferência de áudio para as pessoas que pretende agendar ou liderança de reuniões. Os participantes da reunião não precisam de nenhuma licença atribuída ou configuração adicional.
  
Para as perguntas frequentes sobre Audioconferência, consulte [Perguntas comuns sobre Audioconferência](/MicrosoftTeams/audio-conferencing-common-questions).

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]
  
## <a name="step-1-find-out-if-audio-conferencing-is-available-in-your-countryregion"></a>Etapa 1: Descobrir se a audioconferência está disponível em seu país/região
<a name="__top"> </a>


Acesse [Disponibilidade do país e região para audioconferência e planos de chamada](/microsoftteams/country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans) e selecione seu país ou região para obter informações de disponibilidade sobre a audioconferência, assim como informações sobre as sistema telefônico, planos de chamada, números de chamada tarifada e chamada gratuita, e créditos de comunicação. 
 
## <a name="step-2-get-and-assign-licenses"></a>Etapa 2: Comprar e atribuir licenças
 
1. Para caudioonferências, você precisa de uma licença de cada usuário que irá configurar as reuniões discadas. Para saber quais licenças você precisará comprar para conferência de áudio e quanto eles terá um custo, consulte [Skype para licenciamento de complemento de negócios e equipes da Microsoft](../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md).
        
2. Depois que você adquire as licenças de audioconferência, é preciso atribuí-las às pessoas em sua organização que irão agendar ou realizar as reuniões. Consulte [atribuir ou remover licenças do Office 365 for business](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc) você comprou às pessoas em sua organização que pretende agendar ou líder de reuniões.
    
3. Também é recomendável que você atribua licenças créditos de comunicação (são gratuitas) para as mesmas pessoas a quem você atribuiu as licenças na etapa anterior. Para saber como configurar os créditos de comunicação, consulte [Configurar créditos de comunicação para sua organização](/microsoftteams/set-up-communications-credits-for-your-organization).
    
> [!NOTE]
> Você também pode definir a audioconferência com pagamento por minuto. Clique [aqui](/microsoftteams/audio-conferencing-pay-per-minute) para obter mais informações sobre como usá-los.

## <a name="step-3-get-service-numbers-for-your-conferencing-bridges"></a>Etapa 3: Obtenha números de serviço para suas pontes de conferência
<a name="__top"> </a>

Para audioconferências, você não pode usar números de telefone para usuários; será preciso obter os números de serviço. Você pode obter números de serviço tarifado ou gratuito para suas pontes de conferência. Há três maneiras de obter números de serviço tarifado ou gratuito: 
  
- **Use o Skype para centro de administração de negócios.** Para alguns países/regiões, você pode obter números de serviço para suas pontes de conferência usando o centro de administração do Skype for Business, consulte [Obter números de telefone de serviço](../what-is-phone-system-in-office-365/getting-service-phone-numbers.md).
    
- **Porta de seus números de serviço existente.** Faça a portabilidade ou transfira os números existentes do seu provedor de serviços ou operadora de telefonia atual para o Office 365. Consulte [Transferir números de telefone para o Office 365](/microsoftteams/transfer-phone-numbers-to-office-365) ou [Gerenciar números de telefone para sua organização](/microsoftteams/manage-phone-numbers-for-your-organization) para obter mais informações sobre esse assunto.  
  
- **Usar um formulário de solicitação para novos números.** Às vezes (dependendo do seu país/região) não será possível obter seus números de serviço nova usando o Skype para o Centro de administração de negócios ou, você precisará de números de telefone específico ou códigos de área. Se for o caso, será necessário baixar um formulário e enviá-lo para nós. Para obter mais informações, consulte [Gerenciar números de telefone para sua organização](/microsoftteams/manage-phone-numbers-for-your-organization). 
    
## <a name="step-4-assign-a-service-number-to-the-conferencing-bridge"></a>Etapa 4: Atribuir um número de serviço para a ponte de conferência
<a name="__top"> </a>

Depois de obter seus números de serviço tarifado e/ou gratuito para sua ponte de conferência, você precisa atribuir os números para que possam ser usados em convites de reunião.  

Para atribuir um novo número de telefone para sua ponte de audioconferência:

![logotipo-sfb-30x30.png](../images/sfb-logo-30x30.png) **usando o Skype para o Centro de administração de negócios:**

 Vá para o **Centro de administração do Office 365** > **Admin centrais** > **Skype para negócios** > **voz** > **números de telefone**, selecione o número de telefone e clique em **atribuir**.

Para obter mais detalhes, consulte [alterar os números de telefone na sua ponte de conferência de áudio](/MicrosoftTeams/change-the-phone-numbers-on-your-audio-conferencing-bridge).

## <a name="step-5-set-the-default-and-alternate-languages-for-a-conferencing-bridge"></a>Etapa 5: Definir o padrão e os idiomas alternativos para uma ponte de conferência
<a name="__top"> </a>

Em seguida, você deseja [Definir os idiomas de atendedor automático da audioconferência](../audio-conferencing-in-office-365/set-auto-attendant-languages-for-audio-conferencing.md) que o atende dor automático da audioconferência usa para saudar um chamador quando ele disca para um número de telefone para uma audioconferência. 

![teams-logo-30x30.png](../images/teams-logo-30x30.png) **Usar o centro de administração do Microsoft Teams e do Skype para Business:**

No painel, vá para **Reuniões** > **Pontes de conferência**, selecione o número de telefone da ponte de conferência, clique em **Editar**e escolha o idioma padrão.

![logotipo-sfb-30x30.png](../images/sfb-logo-30x30.png) **usando o Skype para o Centro de administração de negócios:**

Vá para **Centro de administração do Office 365** > **Centros de administração** > **Skype for Business** > **Audioconferência** > **Configurações da ponte da Microsoft**, selecione o número de telefone da ponte de conferência e depois clique em **Definir idiomas**.

## <a name="step-6-set-your-conferencing-bridge-settings"></a>Etapa 6: Definir suas configurações da ponte de conferência
<a name="__top"> </a>
    
Após configurar sua ponte de conferência, verifique se as configurações padrão, como notificações de entrada/saída e o comprimento do PIN, são aquelas que deseja usar; caso contrário, você pode alterá-las. 

![teams-logo-30x30.png](../images/teams-logo-30x30.png) **Usar o centro de administração do Microsoft Teams e do Skype para Business:**

No painel, vá para **Reuniões** > **Pontes de conferência** > **Configurações da ponte**. Esse procedimento abrirá o painel **Configurações da ponte**. Para mais detalhes, consulte [Alterar as configurações de uma ponte de audioconferência](/MicrosoftTeams/change-the-settings-for-an-audio-conferencing-bridge).

![logotipo-sfb-30x30.png](../images/sfb-logo-30x30.png) **usando o Skype para o Centro de administração de negócios:**

Vá para **Centro de administração do Office 365** > **Centros de administração** > **Skype for Business** > **Audioconferência** > **Configurações da ponte da Microsoft**. Esse procedimento abrirá a página de **Configurações da ponte da Microsoft**. Para mais detalhes, consulte [Alterar as configurações de uma ponte de audioconferência](/MicrosoftTeams/change-the-settings-for-an-audio-conferencing-bridge).

## <a name="step-7-assign-dial-in-phone-numbers-for-users-who-lead-meetings"></a>Etapa 7: Atribuir números de telefone para discagem para os usuários que realizarão as reuniões

Após ter criado uma ponte de audioconferênci, você precisará definir números de chamada tarifada e chamada gratuita para seus usuários.

Você precisará fazer isso para todas as pessoas na sua organização que irão agendar ou realizar as reuniões. Para fazer isso:

![teams-logo-30x30.png](../images/teams-logo-30x30.png) **Usar o centro de administração do Microsoft Teams e do Skype para Business:**

No painel, clique em **Usuários**, selecione o usuário na lista, clique em **Editar**, clique em **Editar** ao lado de **Audioconferência**e, em seguida, no painel de **Audioonferência**, escolha um número nas listas **Número de chamada tarifada** e **Número de chamada gratuita**.

![logotipo-sfb-30x30.png](../images/sfb-logo-30x30.png) **usando o Skype para o Centro de administração de negócios:**

Vá para **Centro de administração do Office 365** > **Skype for Business** > **Audioconferência** > **Usuários**e, em seguida, selecione o usuário na lista e clique em **Editar**. Se você precisar de mais detalhes, consulte [Atribuir a Microsoft como o provedor de serviços de audioconferência](../audio-conferencing-in-office-365/assign-microsoft-as-the-audio-conferencing-provider.md).


## <a name="step-8-set-up-meeting-invitations-optional"></a>Etapa 8: Configurar os convites para reuniões (opcional)
<a name="__top"> </a>
 
Os números de discagem que são definidos para o usuário serão adicionados automaticamente aos convites de reunião que são enviados para os participantes da reunião. No entanto, você pode adicionar seus próprios links jurídico, uma mensagem de texto e um pequeno gráfico da empresa. Consulte [Personalizar convites de reunião](../set-up-skype-for-business-online/customize-meeting-invitations.md).
   
## <a name="related-topics"></a>Tópicos relacionados

[Perguntas comuns sobre a Audioconferência](/MicrosoftTeams/audio-conferencing-common-questions)
  
[Configurar o Skype for Business Online](../set-up-skype-for-business-online/set-up-skype-for-business-online.md)
  
[Números de telefone para audioconferência](phone-numbers-for-audio-conferencing.md)
  
[Definir opções para reuniões on-line e chamadas em conferência](https://support.office.com/article/DCD1CA39-0C1F-466C-9573-F04138FEF5E2)
