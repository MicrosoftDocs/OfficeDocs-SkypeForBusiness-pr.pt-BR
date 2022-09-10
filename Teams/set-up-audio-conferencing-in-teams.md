---
title: Configurar a conferência de áudio das equipes da Microsoft
ms.author: heidip
author: MicrosoftHeidi
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
- m365initiative-meetings
audience: Admin
appliesto:
- Microsoft Teams
ms.localizationpriority: medium
f1.keywords:
- CSH
ms.custom:
- Audio Conferencing
- LIL_Placement
description: 'Aprenda a configurar a discagem ou a conferência de áudio para as pessoas da sua empresa que precisam usar um telefone para participar de chamadas em conferência. '
ms.openlocfilehash: 04c29b6eaf13d12bee1395d913519c971c7a25d1
ms.sourcegitcommit: 5abfb6f1abe10b6d32cf6eb97a890cf3138ed0e6
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/10/2022
ms.locfileid: "67642122"
---
# <a name="set-up-audio-conferencing-for-microsoft-teams"></a>Configurar a conferência de áudio do Microsoft Teams

Às vezes, as pessoas da sua organização precisam usar um telefone para ligar para uma reunião. O Microsoft Teams inclui o recurso de conferência de áudio para essa situação! As pessoas podem ligar para as reuniões do Teams usando um telefone, em vez de usar o aplicativo Teams em um dispositivo móvel ou computador.
  
Basta configurar uma audioconferência para as pessoas que planejam agendar ou conduzir reuniões. Os participantes da reunião não precisam de nenhuma licença atribuída ou configuração adicional.
  
Para as perguntas frequentes sobre Audioconferência, consulte [Perguntas comuns sobre Audioconferência](audio-conferencing-common-questions.md).

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]
  
## <a name="step-1-find-out-if-audio-conferencing-is-available-in-your-countryregion"></a>Etapa 1: Descobrir se a audioconferência está disponível em seu país/região

Acesse [Disponibilidade do país e região para audioconferência e planos de chamada](country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md) e selecione seu país ou região para obter informações de disponibilidade sobre a audioconferência, assim como informações sobre as sistema telefônico, planos de chamada, números de chamada tarifada e chamada gratuita, e créditos de comunicação.

## <a name="step-2-get-and-assign-licenses"></a>Etapa 2: Comprar e atribuir licenças

1. Para caudioonferências, você precisa de uma licença de cada usuário que irá configurar as reuniões discadas. Para saber quais licenças você precisa comprar para a audioconferência e quanto elas custarão, consulte [Licenciamento do Microsoft Teams](./teams-add-on-licensing/microsoft-teams-add-on-licensing.md).

    >[!NOTE]
    > A audioconferência está incluída nas licenças do Office 365 Enterprise E5 e como um complemento.

2. Depois de comprar as licenças da audioconferência, você precisará atribuí-las àquelas pessoas na sua organização que irão agendar ou liderar reuniões. Consulte [Atribuir licenças a usuários no Microsoft 365 ou Office 365 para](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc) empresas que você comprou para as pessoas em sua organização que vão agendar ou liderar reuniões.

3. Também é recomendável que você atribua licenças créditos de comunicação (são gratuitas) para as mesmas pessoas a quem você atribuiu as licenças na etapa anterior. Para saber como configurar os créditos de comunicação, consulte [Configurar créditos de comunicação para sua organização](set-up-communications-credits-for-your-organization.md).

   > [!NOTE]
   > Você também pode configurar a [Audioconferencia paga por minuto](audio-conferencing-pay-per-minute.md)

## <a name="step-3-get-service-numbers-for-your-conferencing-bridges"></a>Etapa 3: Obtenha números de serviço para suas pontes de conferência

Para audioconferências, você não pode usar números de telefone para usuários; será preciso obter os números de serviço. Você pode obter números de serviço tarifado ou gratuito para suas pontes de conferência. Há três maneiras de obter números de serviço tarifado ou gratuito:
  
- **Use o centro de administração do Microsoft Teams.**. Em alguns países/regiões, você pode obter números de serviço para suas pontes de conferência usando o centro de administração do Microsoft Teams. Consulte [Obter números dos telefones de serviço](./getting-service-phone-numbers.md).

- **Portar seus números de serviço existentes**. Para portar ou transferir números existentes de seu provedor de serviços ou operadora de telefonia atual para o Microsoft 365 ou Office 365. Você pode consultar [Transferir os números dos telefones ao Teams](phone-number-calling-plans/transfer-phone-numbers-to-teams.md) ou [Gerenciar números de telefone da sua organização](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md) para obter mais informações para ajudá-lo.  
  
- **Use um formulário de solicitação para novos números**. Às vezes (dependendo do seu país/região), você não poderá obter seus novos números de serviço usando o centro de administração do Microsoft Teams ou precisará de números de telefone ou códigos de área específicos. Nesse caso, você precisará fazer o download de um formulário e enviá-lo de volta para nós. Para obter mais informações, consulte [Gerenciar números de telefone para sua organização](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md).

## <a name="step-4-assign-a-service-number-to-the-conferencing-bridge"></a>Etapa 4: Atribuir um número de serviço para a ponte de conferência

Depois de obter seus números de telefone interurbano e/ou gratuito da sua ponte de conferência, você precisa atribuir os números para que possam ser usados nos convites das reuniões.  

Siga essas etapas para atribuir um novo número de telefone à sua ponte de conferência de áudio.

 **Usando o centro de administração do Microsoft Teams**:

 1. Na Página Inicial, vá para **números de telefone** > **de voz**.
 2. Clique no número de telefone e clique em **Atribuir**.

Para obter mais detalhes, consulte [Altere os números de telefone na sua ponte de audioconferência](change-the-phone-numbers-on-your-audio-conferencing-bridge.md).

## <a name="step-5-set-the-default-and-alternate-languages-for-a-conferencing-bridge"></a>Etapa 5: defina os idiomas padrão e alternativos de uma ponte de conferência

 Em seguida, você quer [Definir os idiomas do atendedor automático da audioconferência no Microsoft Teams](set-auto-attendant-languages-for-audio-conferencing-in-teams.md) que o atendedor automático de conferência usa para cumprimentar os chamadores quando eles discam para um número de telefone da audioconferência.

 **Usando o centro de administração do Microsoft Teams**:

1. Da Página Inicial, vá para **pontes de Conferência** > **de Reuniões**.
2. Clique no número do telefone da ponte de conferência, clique em **Editar** e escolha o idioma padrão.

## <a name="step-6-set-your-conferencing-bridge-settings"></a>Etapa 6: Definir suas configurações da ponte de conferência

Após configurar sua ponte de conferência, verifique se as configurações padrão, como notificações de entrada/saída e o comprimento do PIN, são aquelas que deseja usar; caso contrário, você pode alterá-las.

 **Usando o centro de administração do Microsoft Teams**:

1. Da Página Inicial, vá para **pontes de Conferência** > **de Reuniões**.
2. Clique em **Configurações da ponte**. Esse procedimento abrirá o painel **Configurações da ponte**.

Para mais detalhes, consulte [Alterar as configurações de uma ponte de audioconferência](change-the-settings-for-an-audio-conferencing-bridge.md).

## <a name="step-7-assign-dial-in-phone-numbers-for-users-who-lead-meetings"></a>Etapa 7: Atribuir números de telefone para discagem para os usuários que realizarão as reuniões

Consulte Definir [os números de telefone incluídos em convites no Microsoft Teams](set-the-phone-numbers-included-on-invites-in-teams.md).

> [!NOTE]
> Você também pode definir números de telefone adicionando-os à *TeamsAudioconferencingpolicy* e atribuindo a política aos usuários. Os números de telefone de chamada tarifada e gratuita adicionados à política têm precedência sobre os números de telefone definidos individualmente para os usuários por meio do painel de configurações de audioconferência. Se nenhum número de telefone for adicionado à *Teamsaudioconferencingpolicy*, o número de telefone definido individualmente para os usuários por meio do painel de configurações de audioconferência será exibido nas solicitações de reunião do Microsoft Teams. [As configurações de política de audioconferência para números de chamada tarifada](audio-conferencing-toll-free-numbers-policy.md) e gratuita têm mais informações.

> [!IMPORTANT]
> Pode levar até 24 horas para que os números de telefone atribuídos apareçam no convite da reunião. Se você não estiver vendo os números atualizados serem exibidos, aguarde pelo menos 24 horas antes de entrar em contato com o suporte.

## <a name="step-8-set-up-meeting-invitations-optional"></a>Etapa 8: Configurar os convites para reuniões (opcional)

Os números de discagem definidos para o usuário serão adicionados automaticamente aos convites da reunião enviados aos participantes da reunião. No entanto, você pode adicionar seus próprios links jurídico, uma mensagem de texto e um pequeno gráfico da empresa. Consulte [Personalizar convites da reunião](meeting-settings-in-teams.md#customize-meeting-invitations)

## <a name="related-topics"></a>Tópicos relacionados

[Perguntas comuns sobre a Audioconferência](audio-conferencing-common-questions.md)
  
[Números de telefone da audioconferência no Microsoft Teams](phone-numbers-for-audio-conferencing-in-teams.md)
  
[Definir opções de reuniões online e chamadas em conferência](https://support.office.com/article/DCD1CA39-0C1F-466C-9573-F04138FEF5E2)
