---
title: Introdução às Mensagens Seguras para Organizações de Saúde
author: jambirk
ms.author: jambirk
manager: serdars
audience: ITPro
ms.topic: article
ms.service: msteams
search.appverid: MET150
localization_priority: Normal
MS.collection: Teams_ITAdmin_PracticalGuidance
appliesto:
- Microsoft Teams
ms.reviewer: ''
description: Introdução às Mensagens Seguras para Organizações de Saúde
ms.openlocfilehash: 167021c475edd760bf9b56d550616ebb199f2fb5
ms.sourcegitcommit: 55da03c85237b43b848e7ff9b427304c2d9e568f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/04/2019
ms.locfileid: "34681901"
---
# <a name="get-started-with-secure-messaging-for-healthcare-organizations"></a>Introdução às Mensagens Seguras para Organizações de Saúde

As políticas de mensagens são usadas para controlar quais recursos de mensagens de chat e de canal estão disponíveis para os usuários do Microsoft Teams e fazem parte da implantação geral de mensagens seguras para organizações de assistência médica, como hospitais, clínicas ou consultórios do doutor, onde ter uma mensagem removida e em tempo hábil é crucial, como se deve saber quando mensagens cruciais são lidas.

Você pode usar a política padrão ou criar uma ou mais políticas de mensagens personalizadas para as pessoas em sua organização. Depois de criar uma política, você atribuirá a ela um usuário ou grupos de usuários em sua organização. Por exemplo, você pode optar por permitir que apenas determinadas funções de trabalho usem esses recursos (talvez apenas os médicos e os recursos humanos) e outros trabalhadores (como o janitorial ou a cozinha cozinha) para obter um conjunto mais limitado de recursos. Decida por si mesmo o que precisa da sua organização, as orientações aqui são no máximo uma sugestão.

As políticas podem ser facilmente gerenciadas no [centro de administração do Microsoft Teams](http://admin.teams.microsoft.com) , fazendo logon com credenciais de administrador e escolhendo políticas de **mensagens** no painel de navegação à esquerda.

 ![Captura de tela da página de políticas de mensagens](../../media/messaging-policies-image1.png)

Para editar a política de mensagens padrão existente para sua organização, clique na linha **global (padrão para toda** a organização) e faça as alterações. Para criar uma nova política de mensagens personalizada, clique em **nova política** e selecione as configurações. Escolha **salvar** quando terminar.

![Captura de tela das configurações de política de mensagens](../../media/hc-message-policy.png)

As configurações a seguir são de interesse especial para aplicativos de saúde e devem ser consideradas ao criar uma política personalizada usada no campo assistência médica:

## <a name="read-receipts"></a>Confirmações de leitura

- ![O ícone do número 1, fazendo referência a um texto explicativo](../../media/sfbcallout1.png) nas confirmações de leitura anteriores da captura de tela, as confirmações de leitura permite que o remetente de uma mensagem de chat saiba quando a mensagem foi lida pelo destinatário. **** Use essa configuração para especificar se as confirmações de leitura são controladas pelo usuário, habilitadas para todos ou desabilitadas para todos. As confirmações de leitura de mensagens são importantes em organizações de assistência médica porque elas se removem de forma indeterminada sobre se uma mensagem foi lida.

  Para aplicativos de assistência médica, escolha **controlado pelo usuário** ou **habilitado para todos**. Lembre-se de que, ao usar a configuração **habilitado para todos** , a única maneira de definir confirmações para o locatário inteiro é ter apenas uma política de mensagens para todo o locatário (a política padrão nomeada "global (padrão para toda a organização)") ou para ter todas as mensagens as políticas no locatário usam as mesmas configurações para recibos.

  > [!NOTE]
  > Quando as confirmações de leitura são usadas em um chat em grupo grande (com mais de 100 usuários, por exemplo), as mensagens de recebimento podem sobrecarregar as mensagens reais e levar à frustração do usuário de chat. Isso é algo que você precisará para fazer com que os usuários se reconheçam. Um chat em grupo menor (talvez 20 usuários ou menos) faz melhor uso desse recurso.

    *Exemplo de uso sem confirmações de leitura:* Jakob Roth, um paciente de alto risco, é admitido para o hospital.Sófia Krause é um enfermeira que trabalha como parte da equipe inter-disciplinara (IDT) de funcionários médicos, incluindo especialistas diferentes, é atribuído como o principal coordenador responsável por este paciente.  Sófia envia emails e outras mensagens de chat para um grupo de perenção e médicos que usam uma variedade de clientes e aplicativos de mensagens e, muitas vezes, não recebem resposta nem indica se uma mensagem foi lida pelos membros da equipe. Devido a processos de comunicação tangled, o medicação de Jakob é aplicado indevido e seu hospital permanecerá estendido.

    *Exemplo de uso com confirmações de leitura:* Jakob Roth, um paciente de alto risco, é admitido para o hospital.Sófia Krause é um enfermeira que trabalha como parte da equipe inter-disciplinara (IDT) de funcionários médicos, incluindo especialistas diferentes, é atribuído como o principal coordenador responsável por este paciente.  Sófia inicia um chat em grupo com um conjunto de médicos e outros repacientes que trabalharão com o paciente para coordenar o cuidado e iniciar uma triagem de emergência.As hojes e médicos se comunicam e colaboram com o plano de atendimento do paciente em todo o processo de coordenação de atendimento.  Mensagens importantes e urgentes são enviadas pelo 1:1 e conversas de chat em grupo. Sófia usa a funcionalidade de confirmações de leitura para determinar se as mensagens enviadas solicitando suporte são entregues e lidas pelos médicos ou às mensagens de destino. Os resultados do paciente de Jakob são praticamente ótimos, e ele fica mais cedo, porque a equipe de cuidado comunica-se tranqüilamente.

## <a name="priority-notifications"></a>Notificações de prioridade

[!INCLUDE [preview-feature](../../includes/preview-feature.md)]

[!INCLUDE [pri-message-offer](../../includes/pri-message-offer.md)]

- ![Ícone do número 2, fazendo referência a um texto explicativo na](../../media/sfbcallout2.png) captura de tela anterior **os usuários podem enviar notificações de prioridade** Use essa configuração para permitir que os usuários enviem mensagens de chat de prioridade para outros usuários. Esse recurso ajuda a equipe do hospital a enviar uma outra pessoa quando um incidente crítico exige sua atenção. Ao contrário de mensagens regulares "importantes", as notificações de prioridade notificam os usuários repetidamente por um período de 20 minutos ou até que as mensagens sejam retiradas e lidas pelo destinatário, maximizando a probabilidade de que a mensagem seja retirada e seja aprovada em tempo hábil.

  Um administrador pode habilitar ou desabilitar a capacidade dos usuários atribuídos a essa política para enviar notificações de prioridade. Este recurso está ativado por padrão. O destinatário da mensagem de prioridade talvez não tenha a mesma política de mensagens e não terá a opção de desabilitar as mensagens de prioridade de recebimento. Para aplicativos de assistência médica, recomendamos habilitar o recurso para pelo menos alguns usuários, mas você precisará determinar quais deles.

  *Exemplo de uso:* Sófia Krause é readmitting um paciente de alto risco, Jakob Roth. Manuela Carstens, um médico, é o principal médico para este paciente.  Sófia envia uma mensagem para Manuela usando uma notificação de prioridade solicitando ajuda imediata com a triagem de Jakob.  O telefone da Manuela recebe a mensagem, mas Manuela não sente a vibração do telefone e não responde. O Microsoft Teams notifica o Manuela e continuará a renotificá-lo persistentemente até que ele leia a mensagem. Se as confirmações de leitura também estiverem habilitadas, as Sófia podem estar cientes de que a mensagem foi lida por Manuela, mesmo antes de Manuela decidir como responder.

## <a name="related-topics"></a>Tópicos relacionados

- [Gerenciar políticas de mensagens no Teams](../../messaging-policies-in-teams.md)
- [Introdução ao Teams para Organizações de Saúde](teams-in-hc.md)
