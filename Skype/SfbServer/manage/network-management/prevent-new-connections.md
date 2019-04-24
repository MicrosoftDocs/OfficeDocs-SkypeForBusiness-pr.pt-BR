---
title: Impedindo novas conexões
ms.reviewer: ''
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: ''
ms.openlocfilehash: bc9b4a1e7d6e17f09643ff14ac0e69261c326922
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/23/2019
ms.locfileid: "32199017"
---
# <a name="preventing-new-connections-to-skype-for-business-server-for-server-maintenance"></a>Impedindo novas conexões Skype para Business Server para manutenção do servidor


Skype para Business Server permite colocar um servidor offline (por exemplo, para aplicar atualizações de software ou hardware) sem que ocorra perda de serviço aos usuários.

Quando você especifica a opção para evitar novas conexões ou chamadas para um servidor em um pool, ele bloqueia aproveitando quaisquer novas conexões e chamadas assim que você implemente essa opção. Essas novas conexões e as chamadas são roteadas através de outros servidores no pool. Um servidor que está impedindo novas conexões permite que suas sessões em conexões existentes para continuar até que elas terminam naturalmente. Quando todas as sessões existentes tiverem terminado, o servidor está pronto para ser colocado offline.

Quando você evitar novas conexões a um servidor Front-End, alguns Skype para recursos de servidor de negócios e serviços dependem de DNS com carga balanceada para garantir que ele funcione corretamente. Se você não estiver usando o DNS com carga balanceada no pool, conexões por meio desses serviços podem não ser redirecionadas para outros servidores durante o período que o servidor está impedindo novas conexões, e, portanto, quando o servidor for colocado offline algumas sessões e as chamadas podem ser interrompida. Os recursos que dependem de DNS com carga balanceada para garantir que essa opção funcione corretamente são:

  - Atendedor

  - Aplicativo Comunicado de Conferência

  - Aplicativo Grupo de Resposta

  - Aplicativo Comunicado

  - Aplicativo de Estacionamento de Chamada

Para obter detalhes sobre o balanceamento de carga DNS, consulte [requisitos de balanceamento de carga](../../plan-your-deployment/network-requirements/load-balancing.md).

Além de evitar novas conexões para todos os serviços em um servidor executando o Skype para Business Server, você também pode impedir novas conexões para Skype individual para serviços de Business Server. Por exemplo, esse método é útil em uma situação em que você precisa aplicar um Skype para atualização do servidor de negócios que não requer que o servidor inteiro seja encerrado. Observe que quando você impede conexões para um serviço, você deve selecionar um serviço ao serem agrupada e exibido na lista de serviços Windows. Por exemplo, o Skype para serviço de front-end Server de negócios e o agente de coleta de dados de monitoramento são Skype separado para os serviços de Business Server, mas na lista de serviços do Windows estão consolidadas e mostrados como o Skype para negócios servidor Front-End serviço. Você pode impedir novas conexões para o Skype para serviço de negócios servidor Front-End, mas você não pode impedir novas conexões para essas duas Skype individuais de subjacente para serviços de Business Server separadamente.

> [!IMPORTANT]
> Quando você configura um servidor para impedir novas conexões e, em seguida, reiniciar o servidor, por padrão o servidor imediatamente começará aceitando novas conexões após ele ser iniciado. Para impedir isso, defina o servidor só pausar e retomar manualmente, antes de reiniciar o servidor.

## <a name="to-prevent-new-connections-to-skype-for-business-server"></a>Para evitar novas conexões Skype para Business Server

1.  Faça logon no computador local como membro do grupo Administradores.

2.  Abra o console do snap-in Serviços: clique em **Iniciar**, aponte para **Todos os programas**, aponte para **Ferramentas administrativas**e clique em **Serviços**.

3.  Na lista, clique duas vezes o Skype para serviço de Business Server Windows ao qual você deseja evitar novas conexões.

4.  Na caixa de diálogo Propriedades, sob **status de serviço: iniciado**, clique em **Pausar**.

5.  Opcionalmente, mas recomendado, ao lado de **tipo de inicialização**, clique em **Manual**.
    
    > [!IMPORTANT]
    > Quando você configura um servidor para impedir novas conexões e, em seguida, reiniciar o servidor, por padrão o servidor imediatamente começará aceitando novas conexões após ele ser iniciado. Para impedir isso, defina o servidor só pausar e retomar manualmente, antes de reiniciar o servidor.
