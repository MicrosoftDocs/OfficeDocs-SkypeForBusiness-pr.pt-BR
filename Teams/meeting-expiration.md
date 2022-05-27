---
title: Políticas de reunião e expiração de reunião Microsoft Teams
author: mkbond007
ms.author: mabond
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: nej, brgussin
audience: admin
ms.localizationpriority: medium
search.appverid: MET150
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
f1.keywords:
- CSH
ms.custom: ''
description: Saiba como usar as configurações de política de reunião para controlar a expiração da reunião Microsoft Teams.
ms.openlocfilehash: 08cdcd9b7d7f18dafa468bd33ca065dafb5768a6
ms.sourcegitcommit: 296862e02b548f0212c9c70504e65b467d459cc3
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/25/2022
ms.locfileid: "65675353"
---
# <a name="meeting-policies-and-meeting-expiration-in-microsoft-teams"></a>Políticas de reunião e expiração de reunião Microsoft Teams

[As políticas](meeting-policies-overview.md) de reunião Microsoft Teams são usadas para controlar se os usuários em sua organização podem iniciar e agendar reuniões e os recursos que estão disponíveis para os participantes da reunião para reuniões agendadas pelos usuários. Você pode usar a política global (padrão para toda a organização) ou criar e atribuir políticas personalizadas. Gerencie políticas de reunião no centro de administração do Microsoft Teams ou usando os cmdlets [Get](/powershell/module/skype/get-csteamsmeetingpolicy), [New](/powershell/module/skype/new-csteamsmeetingpolicy), [Set](/powershell/module/skype/set-csteamsmeetingpolicy), [Remove](/powershell/module/skype/remove-csteamsmeetingpolicy), [Grant](/powershell/module/skype/grant-csteamsmeetingpolicy) -CsTeamsMeetingPolicy do PowerShell.

As configurações de política de reunião que controlam se os usuários podem iniciar e agendar reuniões e também controlar a expiração de reuniões agendadas pelos usuários. Quando um link de ingresso na reunião e a ID de conferência de uma reunião expiram, ninguém pode ingressar na reunião. As configurações de política de reunião a seguir determinam se os usuários podem iniciar e agendar reuniões Teams. Discutiremos as configurações da reunião neste artigo.

- [Reunir-se agora em canais](meeting-policies-in-teams-general.md#meet-now-in-channels): controla se um usuário pode iniciar uma reunião improvisada em um canal.
- [Agendamento de reunião de canal](meeting-policies-in-teams-general.md#channel-meeting-scheduling): controla se um usuário pode agendar uma reunião em um canal.
- [Agendamento de reunião privada](meeting-policies-in-teams-general.md#private-meeting-scheduling): controla se um usuário pode agendar uma reunião privada no Teams. Uma reunião é particular quando não é publicada em um canal de uma equipe.
- [Outlook adicionar: controla se](meeting-policies-in-teams-general.md#outlook-add-in) um usuário pode agendar uma reunião privada do Outlook. Uma reunião é particular quando não é publicada em um canal de uma equipe.
- [Reunir-se agora em reuniões privadas](meeting-policies-in-teams-general.md#meet-now-in-private-meetings): controla se um usuário pode iniciar uma reunião privada improvisada.

Por padrão, essas configurações estão ativadas. Quando qualquer uma dessas configurações é desativada, qualquer usuário que recebe a política não pode iniciar ou agendar novas reuniões desse tipo. Ao mesmo tempo, os links de ingresso na reunião e as IDs de conferência de todas as reuniões existentes desse tipo que o usuário iniciou ou agendou anteriormente expiram.

Por exemplo, se um usuário receber uma política de reunião na qual essas configurações de política de reunião estão definidas como Ativado e, em seguida,  você desativar a configuração Permitir Reunião agora na configuração de canais, esse usuário não poderá mais iniciar reuniões improvisadas em canais e o canal Reunir agora ingressará em links que o usuário criou anteriormente expiraram. O usuário ainda pode iniciar e agendar outros tipos de reunião e ingressar em reuniões organizadas por outras pessoas.

## <a name="what-happens-when-the-meeting-join-link-and-conference-id-expire"></a>O que acontece quando o link de ingresso na reunião e a ID de conferência expiram?

Quando o link de ingresso na reunião e a ID de conferência de uma reunião expiram, ninguém pode ingressar na reunião. Quando um usuário tenta ingressar na reunião por meio do link ou por telefone, ele receberá uma mensagem informando que a reunião não está mais disponível. Conversas, arquivos, quadros de comunicações, gravações, transcrições e outros conteúdos relacionados à reunião são mantidos e os usuários ainda podem accessá-los.

## <a name="what-happens-when-you-turn-on-and-turn-off-a-meeting-policy-setting"></a>O que acontece quando você ativa e desativa uma configuração de política de reunião?

### <a name="switch-a-meeting-policy-setting-from-on-to-off"></a>Alternar uma configuração de política de reunião de ativado para desativado

Quando uma configuração de política de reunião é definida como **Ativado**, os usuários que recebem a política podem iniciar ou agendar reuniões desse tipo e todos podem ingressar. Quando você alterna a configuração da política de reunião para **Desativado, os** usuários que recebem a política não podem iniciar ou agendar novas reuniões desse tipo, e os links de ingresso na reunião e as IDs de conferência das reuniões existentes agendadas anteriormente pelo usuário expiram.

Tenha em mente que o usuário ainda pode ingressar em reuniões organizadas por outras pessoas.

### <a name="switch-a-meeting-policy-setting-from-off-to-on"></a>Alternar uma configuração de política de reunião de desativado para ativado

Quando você alterna uma configuração de  política de reunião de Desativado para **Ativado, os** usuários que recebem a política podem iniciar ou agendar reuniões desse tipo. Se uma configuração de política de reunião estiver desativada e ativada novamente para um usuário, todas as reuniões agendadas (e expiradas) previamente agendadas (e expiradas) organizadas pelo usuário se tornarão ativas e as pessoas poderão ingressá-las usando o link de ingresso na reunião ou por telefone.  

## <a name="meeting-expiration-scenarios"></a>Cenários de expiração de reunião

Aqui está um resumo de como funciona a expiração da reunião para cada uma das configurações de política de reunião discutidas neste artigo.

|Se você quiser...&nbsp;&nbsp; |Faça isso&nbsp;&nbsp;&nbsp;&nbsp;  |Comportamento de ingresso na reunião&nbsp;&nbsp;&nbsp;&nbsp;  |
|---------------------------|---------------------|---------|
|Expirar reuniões privadas agora iniciadas por um usuário&nbsp;&nbsp;|Desative **o Meet agora em reuniões particulares**.&nbsp;&nbsp;|Ninguém pode ingressar em **reuniões privadas do Meet agora** iniciadas pelo usuário.|
|Expirar reuniões privadas agendadas por um usuário&nbsp;&nbsp;|Desative **o agendamento de reunião privada**  **e desative Outlook suplemento**. &nbsp;&nbsp;|Ninguém pode ingressar em reuniões privadas agendadas pelo usuário. Isso impede que as pessoas ingressem nas seguintes reuniões:<ul><li>Reuniões particulares que ocorreram no passado.</li><li>Reuniões particulares agendadas para o futuro e que ainda não ocorreram.</li><li>Instâncias futuras de reuniões privadas recorrentes.</li></ul><br>O **agendamento de** reuniões **particulares e Outlook suplemento** devem estar desativados para expirar as reuniões privadas agendadas por um usuário. Se uma configuração estiver desativada e a outra estiver ativada, os links de ingresso na reunião e as IDs de conferência das reuniões existentes permanecerão ativos e não expiram.|
|Expirar reuniões **do canal Reunir agora** iniciadas por um usuário&nbsp;&nbsp;|Desative **Reunir agora nos canais e** _desative_ o **agendamento de reunião do Canal**.&nbsp;&nbsp;|Ninguém pode ingressar no canal **Reunir agora reuniões** iniciadas pelo usuário.|
|Expirar reuniões de canal agendadas por um usuário&nbsp;&nbsp;|Desative o **agendamento de reunião do Canal**.&nbsp;&nbsp;|Ninguém pode ingressar em reuniões de canal agendadas pelo usuário. Isso impede que as pessoas ingressem nas seguintes reuniões:<ul><li>Reuniões de canal que ocorreram no passado.</li><li>Reuniões de canal agendadas para o futuro e que ainda não ocorreram.</li><li>Instâncias futuras de reuniões de canal recorrentes.</li></ul>|

Se você quiser que as pessoas acessem reuniões que foram agendadas anteriormente ou iniciadas por um usuário específico, você pode:

- Ative a configuração de política de reunião para esse usuário.
- Desative a configuração de política de reunião para esse usuário e tenha outro usuário que tenha a configuração de política habilitada crie uma nova reunião para substituir a reunião expirada.

> [!NOTE]
> Se a reunião foi enviada por um representante, que recebeu permissões para enviar convites de reunião em nome de outra pessoa, como um gerente, a configuração da política de reunião será aplicada à pessoa que concedeu permissão (o gerente).

## <a name="changes-to-meeting-expiration"></a>Alterações na expiração da reunião

Todas as TMRs (Teams de reunião) recém-criadas terão uma expiração padrão de 120 dias. Isso é ativado por padrão para todos os locatários. Isso significa que, por padrão, todas as TMRs criadas depois que esse recurso foi ativado serão excluídas 120 dias após a data de criação. Os administradores também podem definir reuniões para **nunca expirar automaticamente**. O OneDrive e SharePoint monitorarão a data de validade definida em todas as TMRs e moverão automaticamente as TMRs para a lixeira na data de validade.

> [!NOTE]
> Uma cópia da transcrição da reunião é salva OneDrive SharePoint uma segunda cópia é salva Exchange armazenamento temporário. A cópia do OSDP expira quando o TMR expira automaticamente.

A expiração automática da reunião é um mecanismo leve de manutenção para reduzir a desordem de armazenamento criada por TMRs mais antigas. Em média, em todos os clientes, 96% das TMRs não são observadas após 60 dias e 99% não são observadas após 110 dias. Acreditamos que quase todos os clientes se beneficiarão da carga de armazenamento reduzida em seu locatário removendo gravações que provavelmente não serão observadas novamente após 60 dias. Nossa meta é fornecer uma experiência o mais limpa possível para todos os clientes por padrão.

Use a expiração da reunião para limitar o OneDrive ou SharePoint para o consumo de armazenamento em nuvem orientado por Teams de reunião. Uma gravação típica de reunião consome cerca de 400 MB por hora de gravação.

> [!NOTE]
> A data de expiração padrão máxima para usuários A1 é de 30 dias.

### <a name="expiration-date"></a>Data de validade

- A data de expiração é calculada como  o dia em que ela é criada mais o número padrão de dias definido na política de Teams **pelo administrador**.
- A reprodução não afeta a data de validade.

### <a name="change-the-default-expiration-date"></a>Alterar a data de validade padrão

Os administradores podem editar a configuração de expiração padrão no PowerShell ou no Teams de administração. As alterações só afetarão  as TMRs recém-criadas desse ponto em diante. Ele não afetará as gravações criadas antes dessa data. Os administradores não podem alterar a data de validade em TMRs existentes. Isso é feito para proteger a decisão do usuário que possui a TMR. As reuniões e chamadas podem ser controladas por essa configuração.

O valor da data de validade pode ser definido da seguinte maneira:

- Valor mínimo: **1 dia**
- Valor máximo: **99.999 dias**
- Você também pode definir a data de validade como **-1** para que as gravações nunca expirem.

Exemplo de comando do PowerShell:

```powershell
Set-CsTeamsMeetingPolicy -Identity Global -NewMeetingRecordingExpirationDays 50
```

Você pode definir a data de validade no centro Teams de administração em **Políticas de reunião.** Depois de ativar as **Reuniões expirarem automaticamente,** você terá a opção de definir uma expiração de gravação.

![Administração de tela central da política de expiração da reunião.](media/meeting-expiration-policy.jpg)

### <a name="security-and-compliance"></a>Segurança e conformidade

#### <a name="should-i-rely-on-this-feature-for-strict-security-and-compliance-adherence"></a>Devo contar com esse recurso para uma conformidade estrita de segurança e conformidade?

Não, você não deve confiar nisso para proteção legal, pois os usuários finais podem modificar a data de validade de todas as gravações que eles controlam.

#### <a name="will-a-retention-andor-deletion-policy-ive-set-in-the-security--compliance-center-override-the-teams-meeting-recording-expiration-setting"></a>Uma política de retenção e/ou exclusão que eu defini no Centro de conformidade de segurança & substituirá a configuração Teams de expiração da gravação da reunião?

Sim, todas as políticas definidas no centro de conformidade terão precedência total.

Por exemplo:

- Se você tiver uma política que diz que todos os arquivos em um site devem ser retidos por 100 dias e a configuração de expiração para uma gravação de reunião do Teams for de 30 dias, a gravação será mantida por 100 dias completos.
- Se você tiver uma política de exclusão que diz que todas as gravações de reunião do Teams serão excluídas após cinco dias e você tiver uma configuração de expiração para uma gravação de reunião do Teams de 30 dias, a gravação será excluída após cinco dias.

### <a name="will-this-feature-enforce-file-retention"></a>Esse recurso aplicará a retenção de arquivos?

Não, os arquivos não serão retidos devido a esse recurso ou suas configurações. Se um usuário com permissões de exclusão tentar excluir uma TMR que tenha uma configuração de expiração, a ação de exclusão desse usuário será executada.

### <a name="what-skus-are-required-for-this-feature"></a> Quais SKUs são necessários para esse recurso?

- Todas as SKUs terão esse recurso por padrão.
- A1 os usuários terão o padrão de um período de expiração máximo de 30 dias, mas poderão alterar a data de expiração conforme necessário.

### <a name="what-if-i-want-the-admin-to-have-full-control-over-the-lifecycle-of-meeting-recordings-and-dont-want-to-give-end-users-the-ability-to-override-the-expiration-date"></a>E se eu quiser que o administrador tenha controle total sobre o ciclo de vida das gravações de reunião e não quiser dar aos usuários finais a capacidade de substituir a data de validade?

É recomendável usar as políticas de retenção e/ou exclusão de segurança e/ou exclusão. Essa oferta é destinada a resolver questões legais administrativas e políticas complexas orientadas por SLA.

O recurso de expiração automática destina-se exclusivamente a um mecanismo de manutenção leve para reduzir a desordem de armazenamento criada com base em Teams de reuniões antigas.

### <a name="will-future-tmrs-migrated-from-classic-stream-after-this-feature-is-released-have-auto-expiration-applied-to-them-too"></a>As TMRs futuras migrados do Fluxo Clássico após o lançamento desse recurso também terão a expiração automática aplicada a elas?

Não, as TMRs migradas não virão com uma expiração definida. Em vez disso, incentivamos os administradores a migrar apenas as TMRs que desejam reter. Mais detalhes serão fornecidos na documentação de migração.

### <a name="how-is-this-feature-different-from-the-expiration-message-i-see-when-a-tmr-upload-to-onedrive-and-sharepoint-fails"></a>Como esse recurso é diferente da mensagem de expiração que vejo quando um carregamento de TMR para OneDrive e SharePoint falha?

Quando uma gravação não é carregada no OneDrive ou no SharePoint, o aplicativo Teams exibe uma mensagem no chat de que os usuários têm até 21 dias para baixar a TMR antes que ela seja excluída permanentemente do servidor Teams. Essa experiência de expiração existente devido a carregamentos TMR com falha não está relacionada ao OneDrive e SharePoint recurso de expiração automática que está sendo discutido no documento de ajuda.

### <a name="how-do-i-know-the-distribution-of-tmr-playbacks-so-i-know-what-the-optimal-auto-expiration-default-should-be-for-my-tenant"></a>Como fazer a distribuição de reprodução TMR para que eu saiba qual deve ser o padrão de expiração automática ideal para meu locatário?

1. Localize o vídeo na biblioteca.
1. Selecione **...** >  **Detalhes**
1. Selecione o número de exibições na parte superior do painel de detalhes.

Você verá estatísticas de arquivo que mostram:

- O número de visualizadores exclusivos
- O número total de exibições
- A tendência de visualizadores e exibições dia a dia dos últimos 90 dias
- Retenção de propriedade (qual parte do vídeo foi exibida ou não)

### <a name="when-will-the-file-be-deleted"></a>Quando o arquivo será excluído?

O arquivo será excluído dentro de cinco dias a partir da data de validade, embora essa não seja uma garantia estrita. O proprietário do arquivo receberá uma notificação por email quando a gravação expirar e será direcionado para a lixeira para recuperar a gravação.

> [!NOTE]
> Na data de validade, a gravação é movida para a lixeira e o campo de data de validade é limpo. Se você recuperar a gravação da lixeira, ela não será excluída por esse recurso novamente porque a data de validade foi desmarcada.

## <a name="related-topics"></a>Tópicos relacionados

[Alterar a data de expiração da reunião – controles do usuário final](https://support.microsoft.com/office/record-a-meeting-in-teams-34dfbe7f-b07d-4a27-b4c6-de62f1348c24#bkmk_view_change_expiration_date)

[Gerenciar políticas de reunião no Teams](meeting-policies-overview.md)

[Atribuir políticas aos usuários no Microsoft Teams](policy-assignment-overview.md)

[Visão Geral do PowerShell do Teams](teams-powershell-overview.md)

[Limites e especificações do Microsoft Teams](/microsoftteams/limits-specifications-teams)
