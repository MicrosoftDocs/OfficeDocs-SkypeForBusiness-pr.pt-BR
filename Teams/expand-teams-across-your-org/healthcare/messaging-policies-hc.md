---
title: Mensagens Seguras para organizações de saúde através do Microsoft Teams
author: dstrome
ms.author: dstrome
manager: serdars
audience: ITPro
ms.topic: article
ms.service: msteams
search.appverid: MET150
searchScope:
- Microsoft Teams
- Microsoft Cloud for Healthcare
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection:
- M365-collaboration
- Teams_ITAdmin_Healthcare
- microsoftcloud-healthcare
appliesto:
- Microsoft Teams
ms.reviewer: ''
description: Aprenda a personalizar uma política de Mensagens Seguras para o Microsoft Teams que pode incluir confirmação de leitura e notificações prioritárias.
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: ededfabcca1ab61ec822f201502658f4d8ac498a
ms.sourcegitcommit: cfc48dc03550c093c4405fb5984648188f523699
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/01/2021
ms.locfileid: "60045513"
---
# <a name="secure-messaging-for-healthcare-organizations"></a>Introdução às Mensagens Seguras para organizações de saúde

As políticas de mensagens são usadas para controlar quais os recursos de bate-papo e canal de mensagens estão disponíveis para os usuários do Microsoft Teams e fazem parte da implantação geral do Mensagens Seguras para organizações de saúde, como hospitais, clínicas ou consultórios médicos, onde ter uma mensagem captada e executada em tempo hábil é crucial, assim como saber quando as mensagens cruciais são lidas.

Você pode usar a política global (padrão para toda a organização) ou criar uma ou mais políticas de mensagens personalizadas para as pessoas em sua organização. Os usuários em sua organização obterão automaticamente a política global, a menos que você crie e atribua uma política personalizada. Depois de criar uma política personalizada, você pode atribuí-la a um usuário ou grupo de usuários da organização. Por exemplo, você pode escolher permitir que apenas determinados cargos de trabalho usem esses recursos (talvez apenas médicos e enfermeiras), enquanto outros trabalhadores (como zelador ou equipe de cozinha) tenham um conjunto mais limitado de recursos. Decida você mesmo quais são as necessidades de sua organização, a orientação aqui é no máximo uma sugestão.

As políticas podem ser facilmente gerenciadas no [centro de administração do Microsoft Teams](https://admin.teams.microsoft.com), entrando com as credenciais de administrador e escolhendo as **Políticas de mensagens** no painel de navegação esquerdo.

 :::image type="content" source="../../media/hc-messaging-policy-admin-center-new.png" alt-text="Captura de tela da página Políticas de mensagens." lightbox="../../media/hc-messaging-policy-admin-center-new.png":::
 
 Para editar a política de Mensagens padrão existente para sua organização, clique em **Global (padrão em toda a organização)** e faça as suas alterações. Para criar uma nova política de mensagens personalizada, clique em **Adicionar** e selecione as suas configurações. Escolha **Salvar** quando terminar.

![Captura de tela das configurações de política de mensagens.](../../media/hc-messaging-policy.png)

As configurações a seguir são de interesse especial para os aplicativos de saúde e devem ser consideradas na concepção de uma política customizada para uso no campo de saúde:

## <a name="read-receipts&quot;></a>Confirmação de leitura

A confirmação de leitura permite que o remetente de uma mensagem de bate-papo saiba quando a sua mensagem foi lida pelo destinatário em chats individuais e em grupo de 20 pessoas ou menos. Use esta configuração para especificar se as confirmações de leitura são controladas pelo usuário, ativadas para todos ou desativadas para todos. As confirmações de leitura de mensagem são importantes em organizações de saúde porque eliminam a incerteza sobre se uma mensagem foi lida.

Para aplicativos de saúde, escolha **Controlado pelo usuário** ou **Ativado para todos**. Lembre-se de que, ao usar a configuração **Ativado para todos**, a única maneira de definir confirmações para todos os  locatários é ter apenas uma política de mensagens para todos os locatários (a política padrão denominada &quot;Global - padrão para toda a organização") ou fazer com que todas as políticas de mensagens no locatário usem as mesmas configurações para confirmações. O recurso de confirmação de leitura é mais eficaz quando o recurso está habilitado como **Ativado para todos**.

*Exemplo de uso sem confirmação de leitura:* Jakob Roth, um paciente de alto risco, é internado no hospital.  Sofia Krause é uma enfermeira que trabalha como parte da equipe interdisciplinar (IDT) de profissionais de saúde, que inclui diferentes especialistas, e é designada como coordenadora de cuidados primários responsável por este paciente.  Sofia envia emails e outras mensagens instantâneas para um grupo de enfermeiras e médicos que usam uma variedade de aplicativos e mensagens instantâneas e, geralmente, não obtém resposta ou indicação se uma mensagem foi lida pelos membros da equipe. Devido aos processos de comunicação emaranhados, a medicação de Jakob é mal aplicada e a sua permanência no hospital é prolongada.

*Exemplo de uso com confirmação de leitura:* Jakob Roth, um paciente de alto risco, é internado no hospital.  Sofia Krause é uma enfermeira que trabalha como parte da equipe interdisciplinar (IDT) de profissionais de saúde, que inclui diferentes especialistas, e é designada como coordenadora de cuidados primários responsável por este paciente.  Sofia inicia um chat em grupo com um conjunto de médicos e outras enfermeiras que trabalharão com o paciente para coordenar o atendimento e inicia uma triagem de emergência.  As enfermeiras e médicos se comunicam e colaboram com o plano de cuidados do paciente ao longo do processo de coordenação do atendimento.  As mensagens importantes e urgentes são enviadas por meio de conversas individuais e de chat em grupo. Sofia usa a funcionalidade de confirmação de leitura para determinar se as mensagens enviadas solicitando suporte são entregues e lidas por médicos ou enfermeiras específicos. Os resultados de paciente de Jakob são quase ideais e ele vai para casa mais cedo porque a sua equipe de saúde se comunica sem problemas.

## <a name="send-urgent-messages-using-priority-notifications"></a>Envie mensagens urgentes usando notificações prioritárias

Um usuário pode marcar uma mensagem como *urgente* ao enviar mensagens de chat para outros usuários. Esse recurso ajuda a equipe hospitalar a alertar uns aos outros quando um incidente crítico requer a sua atenção. Ao contrário das mensagens *importantes* regulares, as [notificações prioritárias](https://support.microsoft.com/article/mark-a-message-as-important-or-urgent-in-teams-ea99d5b6-1317-4550-8d75-86ff14cd4462) notificam os usuários a cada dois minutos por até 20 minutos ou até que a mensagem seja captada e lida pelo destinatário, maximizando a probabilidade de que a mensagem seja processada em tempo hábil.

Um administrador pode habilitar ou desabilitar a capacidade dos usuários atribuídos a esta política de enviar notificações prioritárias. Esse recurso está habilitado por padrão. O destinatário da mensagem prioritária pode não ter a mesma política de mensagens e não terá a opção de desativar o recebimento de mensagens prioritárias. Para aplicativos de saúde, recomendamos habilitar o recurso para pelo menos alguns usuários, mas você precisará determinar quais deles.

*Exemplo de uso com confirmação de leitura:* Sofia Krause está readmitindo um paciente de alto risco, Jakob Roth. Manuela Carstens, médica, é a médica responsável pelo atendimento primário deste paciente.  Sofia envia uma mensagem para Manuela usando uma notificação prioritária pedindo ajuda imediata com a triagem de Jakob.  O telefone de Manuela recebe a mensagem, mas Manuela não sentiu a vibração do telefone e não atende. O Teams notifica Manuela novamente e continuará a notificá-la novamente até que ela leia a mensagem. Se as confirmações de leitura também estiverem ativadas, Sofia pode saber que a mensagem foi lida por Manuela, antes mesmo de Manuela decidir como responder.

## <a name="related-topics"></a>Tópicos relacionados

- [Gerenciar políticas de mensagens no Teams](../../messaging-policies-in-teams.md)
- [Introdução ao Teams para Organizações de Saúde](teams-in-hc.md)
