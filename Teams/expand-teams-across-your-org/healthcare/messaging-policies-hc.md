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
ms.openlocfilehash: 2de10ef2d36dce991e6f1cd122a624e17ff7a918
ms.sourcegitcommit: ee3f79ce1b6da0885e1096f9fba894bcff1814da
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/25/2019
ms.locfileid: "33298680"
---
# <a name="get-started-with-secure-messaging-for-healthcare-organizations"></a>Introdução às Mensagens Seguras para Organizações de Saúde

Políticas de mensagens são usadas para controlar quais recursos de mensagens de canal e de bate-papo estão disponíveis para usuários no Microsoft Teams e fazem parte da implantação geral de Secure Messaging para organizações de saúde como hospitais, palestras ou escritórios médico, onde ter uma mensagem buscadas e tratados modo oportuno é crucial, conforme é saber quando cruciais mensagens são lidos.

Você pode usar a política padrão ou criar uma ou mais políticas de mensagens personalizadas para as pessoas na sua organização. Depois de criar uma política, você vai atribuí-lo um usuário ou grupos de usuários em sua organização. Por exemplo, você pode optar por permitir apenas determinadas funções de trabalho usar esses recursos (talvez médicos e enfermeiros somente) e outros trabalhadores (como a equipe da equipe de manutenção ou cozinha) para obter um conjunto limitado de mais de recursos. Decidir sozinho quais as necessidades de sua organização tem, a orientação aqui é, no máximo, uma sugestão.

Políticas podem ser facilmente gerenciadas no [Centro de administração de equipes da Microsoft](http://admin.teams.microsoft.com) log com credenciais de administrador e escolhendo **Políticas de mensagens** no painel de navegação à esquerda.

 ![políticas de mensagens em equipes](../../media/messaging-policies-image1.png)

Para editar a política existente de mensagens padrão para sua organização, clique na linha **Global (padrão de toda a organização)** e faça suas alterações. Para criar uma nova política personalizada de mensagens, clique em **nova diretiva** e selecione suas configurações. Escolha **Salvar** quando terminar.

![Configurações de política de mensagens do setor de saúde](../../media/hc-message-policy.png)

As configurações a seguir são de interesse especial para aplicativos da área de saúde e devem ser consideradas durante a criação de uma política personalizada usada no campo de saúde:

## <a name="read-reciepts"></a>Leia recebimentos

- ![um número](../../media/sfbcallout1.png) confirmações de leitura de **confirmações de leitura** permite que o remetente de uma mensagem de bate-papo saber quando a mensagem foi lido pelo destinatário. Use esta configuração para especificar se a notificação de leitura estão usuário controlados, habilitado para todas as pessoas ou desabilitada para todos. Mensagem lida confirmações são importantes para as organizações de saúde porque eles remover maneira imprecisa sobre se uma mensagem foi lido.

  Para aplicativos da área de saúde, escolha **controlado de usuário** ou **habilitado para todas as pessoas**. Lembre-se de que, ao usar a configuração de **habilitado para todas as pessoas** , a única maneira de definir confirmações para o locatário todo é ter apenas uma diretiva de mensagens para o locatário todo (a política padrão nomeado "Global (padrão de toda a organização)") ou ter todas as mensagens as diretivas no locatário usam as mesmas configurações para confirmações.

  > [!NOTE]
  > Quando confirmações são usadas em um grupo grande de leitura chat (com mais de 100 usuários, por exemplo), o recebimento de mensagens podem sobrecarregar as mensagens reais e implicar aborrecimento de usuário de chat. Isso é algo que você precisará tornar usuários ciente. Um chat de grupo menor (talvez 20 usuários ou menos) faz melhor uso desse recurso.

 *Exemplo de uso sem confirmações de leitura:* Jakob Roth, um paciente de alto risco, é admitido para o hospital.Sófia Krause é enfermeiro trabalhando como parte da equipe entre disciplinar (IDT) dos funcionários médicos, incluindo especialistas de diferentes, é atribuído como o coordenador de atendimento médico de principal responsável por este pacientes.  Sófia envia emails e outras mensagens instantâneas para uma grupos de enfermeiras e médicos que usam uma variedade de aplicativos e clientes de mensagens e obtém frequentemente sem resposta ou indicação se uma mensagem foi lido pelos membros da equipe. Devido aos processos de comunicação tangled, remédios do Jakob é aplicada de maneira inadequado e seu permaneça hospital é estendida.

  *Exemplo de uso com confirmações de leitura:* Jakob Roth, um paciente de alto risco, é admitido para o hospital.Sófia Krause é enfermeiro trabalhando como parte da equipe entre disciplinar (IDT) dos funcionários médicos, incluindo especialistas de diferentes, é atribuído como o coordenador de atendimento médico de principal responsável por este pacientes.  Sófia inicia o chat de grupo com um conjunto de médicos e outros enfermeiros quem estará trabalhando com o paciente coordenar atendimento médico e inicia uma triagem de emergência.Os médicos e enfermeiros se comunicar e colaboram através do plano de atendimento do paciente ao longo do processo de coordenação de atendimento médico.  Mensagens importantes e urgentes são enviadas por meio de 1:1 e conversas de bate-papo de grupo. Sófia usa a funcionalidade de confirmações de leitura para determinar se as mensagens enviadas solicitar suporte são entregues e ler pelos médicos de destino ou enfermeiras. Resultados para os pacientes do Jakob são perto ideal e ele vai antes primário, porque sua equipe de atendimento médico se comunica suavemente.

## <a name="priority-notifications"></a>Notificações de prioridade

[!INCLUDE [preview-feature](../../includes/preview-feature.md)]

- ![número dois](../../media/sfbcallout2.png) **os usuários podem enviar notificações de prioridade** Use esta configuração para permitir que os usuários enviem mensagens de chat de prioridade para outros usuários. Esse recurso ajuda a equipe hospitalar quando um incidente crítico requer sua atenção de alerta entre si. Ao contrário de mensagens "importantes" regulares, notificações de prioridade notificam os usuários repetidamente por um período de 20 minutos ou até que as mensagens são buscadas e lido pelo destinatário, maximizando a probabilidade de que a mensagem é buscada e tratada oportunamente.

  Um administrador pode habilitar ou desabilitar a capacidade dos usuários atribuídos a essa diretiva para enviar notificações de prioridade. A configuração padrão é desabilitada. O destinatário da mensagem prioridade pode não ter a mesma política de mensagens e não terá uma opção para desabilitar o recebimento de mensagens de prioridade. Para aplicativos da área de saúde, recomendamos a habilitação do recurso para pelo menos alguns usuários, mas você precisará determinar quais.

  *Exemplo de uso:* Sófia Krause é readmitting um paciente de alto risco, Jakob Roth. Manuela Carstens, médico, é o médico de atendimento médico de primário para este pacientes.  Sófia envia que uma mensagem para Manuela marcadas como 'Alta prioridade' e necessidade imediata de ajuda com a triagem de Jakob.  Telefone de Manuela recebe a mensagem, mas Manuela não se sentem vibração o telefone e não responder. As equipes novamente notifica Manuela e continuarão a persistentemente notificar novamente até que ele lê a mensagem. Se leitura confirmações também estão habilitadas, Sófia pode estar ciente de que a mensagem foi lido pelo Manuela, até mesmo antes Manuela decidirá como responder.

## <a name="related-topics"></a>Tópicos relacionados

- [Gerenciar políticas de mensagens no Teams](../../messaging-policies-in-teams.md)
- [Introdução ao Teams para Organizações de Saúde](teams-in-hc.md)
