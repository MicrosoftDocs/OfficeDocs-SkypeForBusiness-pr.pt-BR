---
title: Proteger mensagens para organizações de assistência médica usando o Microsoft Teams
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
description: Saiba como personalizar uma política de mensagens seguras para o Microsoft Teams que pode incluir confirmações de leitura e notificações de prioridade.
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 77a2024184cb003d5d0ccb0f2b4715b3a3239955
ms.sourcegitcommit: 62d5ccf10202a50755166e3b8de0bd31d1f94fef
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/28/2020
ms.locfileid: "48790623"
---
# <a name="secure-messaging-for-healthcare-organizations"></a>Mensagens seguras para organizações de assistência médica

As políticas de mensagens são usadas para controlar quais recursos de mensagens de chat e de canal estão disponíveis para os usuários do Microsoft Teams e fazem parte da implantação geral de mensagens seguras para organizações de assistência médica, como hospitais, clínicas ou consultórios do doutor, onde a transmissão de mensagens cruciais e funciona em tempo hábil é fundamental, como se conhece quando mensagens cruciais são lidas.

Você pode usar a política global (padrão para toda a organização) ou criar uma ou mais políticas de mensagens personalizadas para as pessoas em sua organização. Os usuários da sua organização terão automaticamente a política global, a menos que você crie e atribua uma política personalizada. Depois de criar uma política personalizada, atribua a ela um usuário ou grupos de usuários em sua organização. Por exemplo, você pode optar por permitir que apenas determinadas funções de trabalho usem esses recursos (talvez apenas os médicos e os recursos humanos) e outros trabalhadores (como o janitorial ou a cozinha cozinha) para obter um conjunto mais limitado de recursos. Decida por si mesmo o que precisa da sua organização, as orientações aqui são no máximo uma sugestão.

As políticas podem ser facilmente gerenciadas no [centro de administração do Microsoft Teams](https://admin.teams.microsoft.com) , fazendo logon com credenciais de administrador e escolhendo **políticas de mensagens** no painel de navegação à esquerda.

 ![Captura de tela da página de políticas de mensagens](../../media/hc-messaging-policy-admin-center.png)

Para editar a política de mensagens padrão existente para sua organização, clique em **global (padrão para toda** a organização) e faça as alterações. Para criar uma nova política de mensagens personalizada, clique em **Adicionar** e, em seguida, selecione as configurações. Escolha **Salvar** quando terminar.

![Captura de tela das configurações de política de mensagens](../../media/hc-messaging-policy.png)

As configurações a seguir são de interesse especial para aplicativos de saúde e devem ser consideradas ao criar uma política personalizada usada no campo assistência médica:

## <a name="read-receipts"></a>Confirmações de leitura

Confirmações de leitura permite que o remetente de uma mensagem de chat saiba quando a mensagem foi lida pelo destinatário no 1:1 e chats em grupo 20 pessoas ou menos. Use esta configuração para especificar se as confirmações de leitura são controladas pelo usuário, ativadas para todos ou desativadas para todos. As confirmações de leitura de mensagens são importantes em organizações de assistência médica porque elas se removem de forma indeterminada sobre se uma mensagem foi lida.

Para aplicativos de saúde, escolha o **usuário controlado** ou **ativado para todos** . Lembre-se de que, ao usar a configuração **ativado para todos** , a única maneira de definir confirmações para o locatário inteiro é ter apenas uma política de mensagens para todo o locatário (a política padrão denominada "global (padrão para toda a organização)") ou para que todas as políticas de mensagens no locatário usem as mesmas configurações para recibos. O recurso de confirmações de leitura é mais eficaz quando o recurso está habilitado como **Ativado para todos** .

*Exemplo de uso sem confirmações de leitura:* Jakob Roth, um paciente de alto risco, é admitido para o hospital.  Sófia Krause é um enfermeira que trabalha como parte da equipe inter-disciplinara (IDT) de funcionários médicos, incluindo especialistas diferentes, é atribuído como o principal coordenador responsável por este paciente.  Sófia envia emails e outras mensagens de chat para um grupo de perenção e médicos que usam uma variedade de clientes e aplicativos de mensagens e, muitas vezes, não recebem resposta nem indica se uma mensagem foi lida pelos membros da equipe. Devido a processos de comunicação tangled, o medicação de Jakob é aplicado indevido e seu hospital permanecerá estendido.

*Exemplo de uso com confirmações de leitura:* Jakob Roth, um paciente de alto risco, é admitido para o hospital.  Sófia Krause é um enfermeira que trabalha como parte da equipe inter-disciplinara (IDT) de funcionários médicos, incluindo especialistas diferentes, é atribuído como o principal coordenador responsável por este paciente.  Sófia inicia um chat em grupo com um conjunto de médicos e outros repacientes que trabalharão com o paciente para coordenar o cuidado e iniciar uma triagem de emergência.  As hojes e médicos se comunicam e colaboram com o plano de atendimento do paciente em todo o processo de coordenação de atendimento.  Mensagens importantes e urgentes são enviadas pelo 1:1 e conversas de chat em grupo. Sófia usa a funcionalidade de confirmações de leitura para determinar se as mensagens enviadas solicitando suporte são entregues e lidas pelos médicos ou às mensagens de destino. Os resultados do paciente de Jakob são quase ótimos, e ele fica mais cedo porque sua equipe de saúde se comunica tranqüilamente.

## <a name="send-urgent-messages-using-priority-notifications"></a>Enviar mensagens urgentes usando as notificações de prioridade

Um usuário pode marcar uma mensagem como *urgente* ao enviar mensagens de chat para outros usuários. Esse recurso ajuda a equipe do hospital a enviar uma outra pessoa quando um incidente crítico exige sua atenção. Ao contrário *das mensagens comuns comuns, as* [notificações de prioridade](https://support.microsoft.com/article/mark-a-message-as-important-or-urgent-in-teams-ea99d5b6-1317-4550-8d75-86ff14cd4462) notificam os usuários a cada dois minutos por até 20 minutos ou até que a mensagem seja retirada e lida pelo destinatário, maximizando a probabilidade de que a mensagem seja acionada de forma oportuna.

Um administrador pode habilitar ou desabilitar a capacidade dos usuários atribuídos a essa política para enviar notificações de prioridade. Este recurso está ativado por padrão. O destinatário da mensagem de prioridade talvez não tenha a mesma política de mensagens e não terá a opção de desabilitar as mensagens de prioridade de recebimento. Para aplicativos de assistência médica, recomendamos habilitar o recurso para pelo menos alguns usuários, mas você precisará determinar quais deles.

*Exemplo de uso:* Sófia Krause é readmitting um paciente de alto risco, Jakob Roth. Manuela Carstens, um médico, é o principal médico para este paciente.  Sófia envia uma mensagem para Manuela usando uma notificação de prioridade solicitando ajuda imediata com a triagem de Jakob.  O telefone da Manuela recebe a mensagem, mas Manuela não sente a vibração do telefone e não responde. O Microsoft Teams notifica o Manuela e continuará a renotificá-lo persistentemente até que ele leia a mensagem. Se as confirmações de leitura também estiverem habilitadas, as Sófia podem estar cientes de que a mensagem foi lida por Manuela, mesmo antes de Manuela decidir como responder.

## <a name="related-topics"></a>Tópicos relacionados

- [Gerenciar políticas de mensagens no Teams](../../messaging-policies-in-teams.md)
- [Introdução ao Teams para Organizações de Saúde](teams-in-hc.md)
