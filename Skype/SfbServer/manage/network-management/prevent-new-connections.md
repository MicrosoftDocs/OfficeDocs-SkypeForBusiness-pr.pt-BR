---
title: Impedir novas conexões
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
description: ''
ms.openlocfilehash: c776c915247533641bc92d1a5458daf671bf6a04
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/04/2021
ms.locfileid: "60759723"
---
# <a name="preventing-new-connections-to-skype-for-business-server-for-server-maintenance"></a>Impedir que novas conexões Skype for Business Server manutenção do servidor


Skype for Business Server permite que você tire um servidor offline (por exemplo, para aplicar atualizações de software ou hardware) sem qualquer perda de serviço para os usuários.

Quando você especifica a opção para impedir novas conexões ou chamadas a um servidor em um pool, ele para de aceitar novas conexões e chamadas assim que você implementa essa opção. As novas conexões e chamadas são roteadas através de outros servidores no pool. Um servidor que está impedindo novas conexões permite que suas sessões em conexões existentes continuem até terminarem de modo natural. Quando todas as sessões existentes são concluídas, o servidor está pronto para ser colocado offline.

Quando você impede novas conexões com um Servidor Front-End, alguns recursos e serviços Skype for Business Server dependem do balanceamento de carga DNS para garantir que ele funcione corretamente. Se você não estiver usando o balanceamento de carga DNSno pool, as conexões por meio desses serviços poderão não ser redirecionados para outros servidores durante o período no qual o servidor está impedindo novas conexões e, portanto, quando o servidor é colocado offline, algumas sessões e chamadas podem ser interrompidas. Estes são os recursos que dependem do balanceamento de carga DNS para garantir que esta opção funcione corretamente:

  - Attendant

  - Aplicativo Comunicado de Conferência

  - Aplicativo Grupo de Resposta

  - Aplicativo de comunicado

  - Call Park application

Para obter detalhes sobre o balanceamento de carga DNS, consulte [Requisitos de balanceamento de carga](../../plan-your-deployment/network-requirements/load-balancing.md).

Além de impedir novas conexões para todos os serviços em um servidor que executa Skype for Business Server, você também pode impedir novas conexões para serviços Skype for Business Server individuais. Por exemplo, esse método é útil em uma situação em que você precisa aplicar uma atualização Skype for Business Server que não exige que todo o servidor seja desligado. Observe que, quando você impede conexões com um serviço, deve selecionar um serviço que é agrupado e exibido na lista de serviços do Windows. Por exemplo, o serviço Skype for Business Server Front-End e o agente de coleta de dados para Monitoramento são serviços Skype for Business Server separados, mas na lista de serviços do Windows eles são consolidados e mostrados como o Skype for Business Server Front-End service. Você pode impedir novas conexões para o serviço Skype for Business Server front-end, mas não pode impedir novas conexões para esses dois serviços de Skype for Business Server individuais separadamente.

> [!IMPORTANT]
> Quando você define um servidor para impedir novas conexões e reiniciar o servidor, por padrão, o servidor começa imediatamente a aceitar novas conexões depois de ser inicializado. Para evitar isso, defina o servidor para apenas pausar e reiniciar manualmente antes de reiniciá-lo.

## <a name="to-prevent-new-connections-to-skype-for-business-server"></a>Para impedir que novas conexões Skype for Business Server

1.  Faça logoff no computador local como membro do grupo Administradores.

2.  Abra o console de snap-in Serviços: **clique** em Iniciar , aponte para **Todos** os Programas, aponte para **Ferramentas** Administrativas e clique em **Serviços**.

3.  Na lista, clique duas vezes no serviço Skype for Business Server Windows para o qual você deseja impedir novas conexões.

4.  Na caixa de diálogo Propriedades, em **Status do serviço: Iniciado,** clique em **Pausar**.

5.  Opcionalmente, mas recomendado, ao lado de **Tipo de Inicialização**, clique em **Manual**.
    
    > [!IMPORTANT]
    > Quando você define um servidor para impedir novas conexões e reiniciar o servidor, por padrão, o servidor começa imediatamente a aceitar novas conexões depois de ser inicializado. Para evitar isso, defina o servidor para apenas pausar e reiniciar manualmente antes de reiniciá-lo.
