---
title: Políticas de reunião e expiração de reunião Microsoft Teams
author: HowlinWolf-92
ms.author: v-mahoffman
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: nej
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
ms.openlocfilehash: 8768410666d003f12cffb80995981b887059f93a
ms.sourcegitcommit: 7cc7e237b0da270c9cf4a3e535db16dd113e4300
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/25/2021
ms.locfileid: "61178012"
---
# <a name="meeting-policies-and-meeting-expiration-in-microsoft-teams"></a>Políticas de reunião e expiração de reunião Microsoft Teams

[As políticas de](meeting-policies-overview.md) reunião Microsoft Teams são usadas para controlar se os usuários em sua organização podem iniciar e agendar reuniões e os recursos disponíveis para os participantes da reunião para reuniões agendadas pelos usuários. Você pode usar a política global (padrão para toda a organização) ou criar e atribuir políticas personalizadas. Você gerencia políticas de reunião no centro de administração do Microsoft Teams ou usando os cmdlets [Get](/powershell/module/skype/get-csteamsmeetingpolicy), [New](/powershell/module/skype/new-csteamsmeetingpolicy), [Set](/powershell/module/skype/set-csteamsmeetingpolicy), [Remove](/powershell/module/skype/remove-csteamsmeetingpolicy), [Grant](/powershell/module/skype/grant-csteamsmeetingpolicy) -CsTeamsMeetingPolicy PowerShell.

As configurações de política de reunião que controlam se os usuários podem iniciar e agendar reuniões e também controlar a expiração das reuniões agendadas pelos usuários. Quando um link de junção de reunião e a ID de conferência de uma reunião expiram, ninguém pode participar da reunião. As configurações de política de reunião a seguir determinam se os usuários podem iniciar e agendar reuniões em Teams. Discutimos as configurações de reunião neste artigo.

- [Reunir agora em canais](meeting-policies-in-teams-general.md#meet-now-in-channels): controla se um usuário pode iniciar uma reunião improvisada em um canal.
- [Agendamento de reunião do canal](meeting-policies-in-teams-general.md#channel-meeting-scheduling): controla se um usuário pode agendar uma reunião em um canal.
- [Agendamento de reuniões privadas](meeting-policies-in-teams-general.md#private-meeting-scheduling): controla se um usuário pode agendar uma reunião privada no Teams. Uma reunião é particular quando não é publicada em um canal de uma equipe.
- [Outlook adicionar :](meeting-policies-in-teams-general.md#outlook-add-in)controla se um usuário pode agendar uma reunião privada de Outlook. Uma reunião é particular quando não é publicada em um canal de uma equipe.
- [Reunir-se agora em reuniões privadas](meeting-policies-in-teams-general.md#meet-now-in-private-meetings): controla se um usuário pode iniciar uma reunião privada improvisada.

Por padrão, essas configurações estão em. Quando qualquer uma dessas configurações é desligada, qualquer usuário que recebe a política não pode iniciar ou agendar novas reuniões desse tipo. Ao mesmo tempo, os links de junção de reunião e as IDs de conferência de todas as reuniões existentes desse tipo que o usuário iniciou ou programou expiram anteriormente.

Por exemplo, se um usuário recebe uma política de reunião na qual essas configurações  de política de reunião estão definidas como **On** e, em seguida, você desliga a configuração Permitir Reunir agora em canais, esse usuário não pode mais iniciar reuniões improvisadas em canais e o canal Reunir agora inserir links que o usuário criou anteriormente estão expirados. O usuário ainda pode iniciar e agendar outros tipos de reunião e participar de reuniões organizadas por outras pessoas.

## <a name="what-happens-when-the-meeting-join-link-and-conference-id-expire"></a>O que acontece quando o link de junção de reunião e a ID da conferência expiram?

Quando o link de junção de reunião e a ID de conferência de uma reunião expiram, ninguém pode participar da reunião. Quando um usuário tenta ingressar na reunião por meio do link ou por telefone, ele receberá uma mensagem informando que a reunião não está mais disponível. Conversas, arquivos, quadro de diálogo, gravações, transcrições e outros conteúdos relacionados à reunião são mantidos e os usuários ainda podem acessá-los.

## <a name="what-happens-when-you-turn-on-and-turn-off-a-meeting-policy-setting"></a>O que acontece quando você ativar e desativar uma configuração de política de reunião?

### <a name="switch-a-meeting-policy-setting-from-on-to-off"></a>Alternar uma configuração de política de reunião de um para outro

Quando uma configuração de política de reunião é definida como **On**, os usuários que são atribuídos à política podem iniciar ou agendar reuniões desse tipo e todos podem ingressar. Quando você alterna a configuração da política de reunião para Off **,** os usuários que são atribuídos à política não podem iniciar ou agendar novas reuniões desse tipo, e os links de junção de reunião e as IDs de conferência de reuniões existentes que o usuário agendava anteriormente expiram.

Lembre-se de que o usuário ainda pode participar de reuniões organizadas por outras pessoas.

### <a name="switch-a-meeting-policy-setting-from-off-to-on"></a>Alternar uma configuração de política de reunião de off para on

Quando você alterna uma configuração de política de reunião de **Off** para **On**, os usuários que são atribuídos à política podem iniciar ou agendar reuniões desse tipo. Se uma configuração de política de reunião estiver desligada e, em seguida, ativa novamente para um usuário, todas as reuniões agendadas (e expiradas) anteriormente organizadas pelo usuário se tornam ativas e as pessoas podem ingressar neles usando o link de participação da reunião ou por telefone.  

## <a name="meeting-expiration-scenarios"></a>Cenários de expiração de reunião

Aqui está um resumo de como funciona a expiração da reunião para cada uma das configurações de política de reunião discutidas neste artigo.

|Se você quiser...&nbsp;&nbsp; |Faça isso&nbsp;&nbsp;&nbsp;&nbsp;  |Comportamento de junção de reunião&nbsp;&nbsp;&nbsp;&nbsp;  |
|---------------------------|---------------------|---------|
|Expire private Meet now meetings started by a user&nbsp;&nbsp;|Desativar o **Meet agora em reuniões privadas.**&nbsp;&nbsp;|Ninguém pode participar de reuniões **privadas do Meet now** iniciadas pelo usuário.|
|Expirar reuniões privadas agendadas por um usuário&nbsp;&nbsp;|Desativar o **agendamento de reunião privada** _e_ desativar Outlook **de complemento**. &nbsp;&nbsp;|Ninguém pode participar de reuniões privadas agendadas pelo usuário. Isso impede que as pessoas participem das seguintes reuniões:<ul><li>Reuniões privadas que ocorreram no passado.</li><li>Reuniões privadas agendadas para o futuro e que ainda não ocorreram.</li><li>Instâncias futuras de reuniões privadas recorrentes.</li></ul><br>Tanto **o agendamento de** reuniões **particulares quanto Outlook o complemento** devem estar desligados para expirar as reuniões privadas agendadas por um usuário. Se uma configuração estiver desligada e a outra estiver ativa, os links de junção de reunião e as IDs de conferência de reuniões existentes permanecerão ativos e não expiram.|
|Expire channel **Reunir agora reuniões** iniciadas por um usuário&nbsp;&nbsp;|Desativar Atender **agora em canais e** _desativar_ o agendamento de reunião **do Canal**.&nbsp;&nbsp;|Ninguém pode ingressar no canal **Reunir agora reuniões** iniciadas pelo usuário.|
|Expirar reuniões de canal agendadas por um usuário&nbsp;&nbsp;|Desativar o **agendamento de reunião do Canal**.&nbsp;&nbsp;|Ninguém pode participar de reuniões de canal agendadas pelo usuário. Isso impede que as pessoas participem das seguintes reuniões:<ul><li>Reuniões de canal que ocorreram no passado.</li><li>Reuniões de canal agendadas para o futuro e que ainda não ocorreram.</li><li>Instâncias futuras de reuniões de canal recorrentes.</li></ul>|

Se você quiser que as pessoas acessem reuniões que foram agendadas anteriormente ou iniciadas por um usuário específico, você pode:

- A opção Ativar a configuração da política de reunião para esse usuário.
- Desativar a configuração da política de reunião para esse usuário e ter outro usuário com a configuração de política habilitada criar uma nova reunião para substituir a reunião expirada.

> [!NOTE]
> Se a reunião foi enviada por um representante, que recebeu permissões para enviar convites de reunião em nome de outra pessoa, como um gerente, a configuração da política de reunião será aplicada à pessoa que concedeu permissão (o gerente).

## <a name="changes-to-meeting-expiration"></a>Alterações na expiração da reunião

Todas as gravações Teams de reunião (TMRs) recém-criadas terão um vencimento padrão de 60 dias. Isso está em uso por padrão para todos os locatários. Isso significa que, por padrão,  todas as TMRs criadas depois que esse recurso foi ligado serão excluídas 60 dias após a data de criação. Os administradores também podem definir reuniões para **nunca expirar automaticamente.** O OneDrive e o SharePoint monitorarão a data de expiração definida em todas as TMRs e moverão automaticamente as TMRs para a lixeira na data de expiração.

A expiração automática da reunião é um mecanismo de limpeza leve para reduzir a desordem de armazenamento criada por TMRs mais antigos. Em média, em todos os clientes, 99% das TMRs não são observadas após 60 dias. Acreditamos que quase todos os clientes se beneficiarão da carga de armazenamento reduzida em seu locatário removendo gravações que provavelmente não serão assistidas novamente após 60 dias. Nosso objetivo é fornecer uma experiência o mais limpa possível para todos os clientes por padrão.

Use a expiração da reunião para limitar o OneDrive ou SharePoint para o consumo de armazenamento na nuvem impulsionado por Teams de reunião. Uma gravação típica de reunião consome cerca de 400 MB por hora de gravação.

> [!NOTE]
> A data de expiração padrão máxima para usuários A1 é de 30 dias.

### <a name="expiration-date"></a>Data de expiração

- A data de expiração é calculada como **o** dia em que é criada, mais o número padrão de dias definido na política de Teams **pelo administrador**.
- A reprodução não afeta a data de expiração.

### <a name="change-the-default-expiration-date"></a>Alterar a data de expiração padrão

Os administradores podem editar a configuração de expiração padrão no PowerShell ou no Teams de administração. Quaisquer alterações só terão efeito *nas* TMRs recém-criadas desse ponto em diante. Ele não afetará as gravações criadas antes dessa data. Os administradores não podem alterar a data de expiração em TMRs existentes. Isso é feito para proteger a decisão do usuário proprietário da TMR. As reuniões e chamadas podem ser controladas por essa configuração.

O valor da data de expiração pode ser definido da seguinte forma:

- Valor mínimo: **1 dia**
- Valor máximo: **99.999 dias**
- Você também pode definir a data de expiração como **-1** para que as gravações nunca expirem.

Exemplo de comando do PowerShell:

```powershell
Set-CsTeamsMeetingPolicy -Identity Global -NewMeetingRecordingExpirationDays 50
```

Você pode definir a data de expiração no Teams de administração em **Políticas de reunião.** Depois que você ativar **reuniões expirar automaticamente,** você terá a opção de definir uma expiração de gravação.

![Captura de tela do Centro de administração da política de expiração de reunião.](media/meeting-expiration-policy.jpg)

### <a name="security-and-compliance"></a>Segurança e conformidade

#### <a name="should-i-rely-on-this-feature-for-strict-security-and-compliance-adherence"></a>Devo contar com esse recurso para uma rigorosa adesão à segurança e à conformidade?

Não, você não deve depender disso para proteção legal, pois os usuários finais podem modificar a data de expiração de todas as gravações que eles controlam.

#### <a name="will-a-retention-andor-deletion-policy-ive-set-in-the-security--compliance-center-override-the-teams-meeting-recording-expiration-setting"></a>Será que uma política de retenção & e/ou exclusão que eu defini no Centro de Conformidade e Segurança substituirá a configuração de Teams de expiração de gravação de reunião?

Sim, todas as políticas definidas no centro de conformidade terão precedência total.

Por exemplo:

- Se você tiver uma política que diga que todos os arquivos em um site devem ser mantidos por 100 dias, e a configuração de expiração para uma gravação de reunião do Teams for de 30 dias, a gravação será mantida pelos 100 dias completos.
- Se você tiver uma política de exclusão que diga que todas as gravações de reunião Teams serão excluída Teams s após cinco dias e você tiver uma configuração de expiração para uma gravação de reunião de 30 dias, a gravação será excluída após cinco dias.

### <a name="will-this-feature-enforce-file-retention"></a>Esse recurso aplicará a retenção de arquivos?

Não, os arquivos não serão mantidos devido a esse recurso ou suas configurações. Se um usuário com permissões de exclusão tentar excluir um TMR que tenha uma configuração de expiração, a ação de exclusão desse usuário será executada.

### <a name="what-skus-are-required-for-this-feature"></a> Quais SKUs são necessários para esse recurso?

- Todas as SKUs terão esse recurso por padrão.
- Os usuários A1 serão padrão para um período máximo de expiração de 30 dias, mas poderão alterar a data de expiração conforme necessário.

### <a name="what-if-i-want-the-admin-to-have-full-control-over-the-lifecycle-of-meeting-recordings-and-dont-want-to-give-end-users-the-ability-to-override-the-expiration-date"></a>E se eu quiser que o administrador tenha controle total sobre o ciclo de vida das gravações de reunião e não quiser dar aos usuários finais a capacidade de substituir a data de expiração?

Recomendamos usar as políticas de retenção e/ou exclusão de Segurança e Conformidade. Essa oferta é destinada a resolver questões legais administrativas e políticas complexas orientadas por SLA.

O recurso de expiração automática é destinado exclusivamente como um mecanismo de limpeza leve para reduzir a desordem de armazenamento criada a partir de gravações de reuniões antigas Teams reuniões.

### <a name="will-future-tmrs-migrated-from-classic-stream-after-this-feature-is-released-have-auto-expiration-applied-to-them-too"></a>As TMRs futuras migrados do Fluxo Clássico após o lançamento desse recurso também terão a expiração automática aplicada a elas?

Não, as TMRs migradas não virão com uma expiração definida. Em vez disso, incentivamos os administradores a migrar apenas as TMRs que desejam reter. Mais detalhes serão fornecidos na documentação de migração.

### <a name="how-is-this-feature-different-from-the-expiration-message-i-see-when-a-tmr-upload-to-onedrive-and-sharepoint-fails"></a>Como esse recurso é diferente da mensagem de expiração que vejo quando um carregamento TMR para OneDrive e SharePoint falha?

Quando uma gravação falha ao carregar no OneDrive ou no SharePoint, o aplicativo Teams exibe uma mensagem no chat de que os usuários têm até 21 dias para baixar a TMR antes de ser excluída permanentemente do servidor Teams. Essa experiência de expiração existente devido a carregamentos TMR com falha não está relacionada ao recurso OneDrive e SharePoint de expiração automática que está sendo discutido no documento de ajuda.

## <a name="related-topics"></a>Tópicos relacionados

[Alterar a data de expiração da reunião - controles do usuário final](https://support.microsoft.com/office/record-a-meeting-in-teams-34dfbe7f-b07d-4a27-b4c6-de62f1348c24#bkmk_view_change_expiration_date)

[Gerenciar políticas de reunião no Teams](meeting-policies-overview.md)

[Atribuir políticas aos usuários no Microsoft Teams](policy-assignment-overview.md)

[Visão Geral do PowerShell do Teams](teams-powershell-overview.md)


