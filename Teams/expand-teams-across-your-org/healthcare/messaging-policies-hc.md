---
title: Sistema de Mensagens Seguras para organizações de saúde usando o Microsoft Teams
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
localization_priority: Normal
ms.collection:
- M365-collaboration
- Teams_ITAdmin_Healthcare
- microsoftcloud-healthcare
appliesto:
- Microsoft Teams
ms.reviewer: ''
description: Saiba como personalizar uma política de Mensagens Seguras do Microsoft Teams que pode incluir recibos de leitura e notificações de prioridade.
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 77a2024184cb003d5d0ccb0f2b4715b3a3239955
ms.sourcegitcommit: 62d5ccf10202a50755166e3b8de0bd31d1f94fef
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/28/2020
ms.locfileid: "48790623"
---
# <a name="secure-messaging-for-healthcare-organizations"></a>Sistema de Mensagens Seguras para organizações de saúde

As políticas de mensagens são usadas para controlar quais recursos de mensagens de chat e canal estão disponíveis para os usuários no Microsoft Teams e fazem parte da implantação geral do Sistema de Mensagens Seguras para organizações de saúde como Hospital, médicos ou consultórios médicos, onde ter uma mensagem escolhida e agido em tempo hábil é crucial, assim como saber quando as mensagens cruciais são lidas.

Você pode usar a política global (padrão de toda a organização) ou criar uma ou mais políticas de mensagens personalizadas para as pessoas em sua organização. Os usuários em sua organização obterão automaticamente a política global, a menos que você crie e atribua uma política personalizada. Depois de criar uma política personalizada, atribua a ela um usuário ou grupos de usuários em sua organização. Por exemplo, você pode optar por permitir que apenas determinadas funções de trabalho usem esses recursos (talvez apenas médicos e médicos) e outros trabalhadores (como a equipe de limpeza ou cozinha) para obter um conjunto mais limitado de recursos. Decida por si mesmo quais são as necessidades que sua organização tem, a orientação aqui é, no máximo, uma sugestão.

As políticas podem ser facilmente gerenciadas no Centro de  administração do [Microsoft Teams,](https://admin.teams.microsoft.com) entrando com credenciais de administrador e escolhendo políticas de mensagens no painel de navegação à esquerda.

 ![Captura de tela da página Políticas de mensagens](../../media/hc-messaging-policy-admin-center.png)

Para editar a política de Mensagens padrão existente para sua organização, clique em **Global (padrão** em toda a organização) e faça suas alterações. Para criar uma nova política de mensagens personalizada, clique **em Adicionar** e selecione suas configurações. Escolha **Salvar** quando terminar.

![Captura de tela das configurações da política de mensagens](../../media/hc-messaging-policy.png)

As configurações a seguir são de interesse especial para aplicativos de saúde e devem ser consideradas ao criar uma política personalizada usada no campo Saúde:

## <a name="read-receipts"></a>Recibos de leitura

As confirmação de leitura permitem que o remetente de uma mensagem de chat saiba quando sua mensagem foi lida pelo destinatário em 1:1 e chats em grupo com 20 pessoas ou menos. Use esta configuração para especificar se as confirmação de leitura são controladas pelo usuário, para todos ou para todos. As confirmação de leitura de mensagens são importantes nas organizações de saúde porque removem incorretamente se uma mensagem foi lida.

Para aplicativos de saúde, escolha **Usuário controlado ou** Em para **todos.** Esteja ciente de  que, ao usar a configuração Para todos, a única maneira de definir recibos para todo o locatário é ter apenas uma política de mensagens para o locatário inteiro (a política padrão chamada "Global (Padrão de toda a organização)") ou ter todas as políticas de mensagens no locatário usando as mesmas configurações para recibos. O recurso de confirmações de leitura é mais eficaz quando o recurso está habilitado como **Ativado para todos**.

*Exemplo de uso sem recibos de leitura:* Jakob Jakob, um paciente de alto risco, é admitido no hospital.  Ela é uma enfermeira que trabalha como parte da equipe interesquelidade (IDT) de profissionais da área médica, incluindo diferentes especialistas, que é designada como a técnica de atendimento primário responsável por esse paciente.  Ela envia emails e outras mensagens instantâneas para um grupo de médicos e médicos que usam uma variedade de aplicativos e clientes de mensagens e geralmente não recebe nenhuma resposta ou indicação se uma mensagem foi lida pelos membros da equipe. Devido a processos de comunicação emaranhados, a medicação de Jakob foi mal atendia e sua estada no hospital foi estendida.

*Exemplo de uso com recibos de leitura:* Jakob Jakob, um paciente de alto risco, é admitido no hospital.  Ela é uma enfermeira que trabalha como parte da equipe interesquelidade (IDT) de profissionais da área médica, incluindo diferentes especialistas, que é designada como a técnica de atendimento primário responsável por esse paciente.  Ela inicia um chat em grupo com um conjunto de médicos e outras pacientes que trabalharão com o paciente para coordenar o atendimento e iniciar uma triagem de emergência.  Os médicos e os médicos se comunicam e colaboram por meio do plano de atendimento do paciente durante todo o processo de coordenação do cuidado.  As mensagens importantes e urgentes são enviadas por meio de conversas de chat entre duas pessoas e em grupo. Ela usa a funcionalidade de confirmação de leitura para determinar se as mensagens enviadas solicitando suporte são entregues e lidas pelos médicos ou médicos direcionados. Os resultados dos pacientes de Jakob são quase ideais e ele vai para casa mais cedo porque sua equipe de saúde se comunica tranquilamente.

## <a name="send-urgent-messages-using-priority-notifications"></a>Enviar mensagens urgentes usando notificações de prioridade

Um usuário pode marcar uma mensagem como *urgente ao* enviar mensagens de chat para outros usuários. Esse recurso ajuda a equipe do hospital a alertar um ao outro quando um incidente crítico exige sua atenção. Ao  contrário das mensagens importantes [normais,](https://support.microsoft.com/article/mark-a-message-as-important-or-urgent-in-teams-ea99d5b6-1317-4550-8d75-86ff14cd4462) as notificações de prioridade notificam os usuários a cada dois minutos por até 20 minutos ou até que a mensagem seja escolhida e lida pelo destinatário, maximizando a probabilidade de a mensagem ser acionada em tempo hábil.

Um administrador pode habilitar ou desabilitar a capacidade dos usuários atribuídos a essa política de enviar notificações de prioridade. Esse recurso está em uso por padrão. O destinatário da mensagem de prioridade pode não ter a mesma política de mensagens e não terá uma opção para desabilitar o recebimento de mensagens de prioridade. Para aplicativos de saúde, recomendamos habiligá-lo para pelo menos alguns usuários, mas você precisará determinar quais.

*Exemplo de uso:* Jakob Ltda está readmitindo um paciente de alto risco, Jakob Jakob. Manuela Carstens, médica, é a médica da atenção primária desse paciente.  Manuela envia uma mensagem para Manuela usando uma notificação de prioridade solicitando ajuda imediata com a triagem de Jakob.  O telefone de Manuela recebe a mensagem, mas Manuela não sente a vibração do telefone e não responde. O Teams notifica manuela e continua a notificar continuamente até que ela leia a mensagem. Se as confirmação de leitura também estão habilitadas, Manuela pode estar ciente de que a mensagem foi lida, mesmo antes de Manuela decidir como responder.

## <a name="related-topics"></a>Tópicos relacionados

- [Gerenciar políticas de mensagens no Teams](../../messaging-policies-in-teams.md)
- [Introdução ao Teams para Organizações de Saúde](teams-in-hc.md)
