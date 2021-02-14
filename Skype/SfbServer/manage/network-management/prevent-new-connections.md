---
title: Impedir novas conexões
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: ''
ms.openlocfilehash: 3f2ca560f934f5b907d05a1f768a0cadd8435f2a
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49823461"
---
# <a name="preventing-new-connections-to-skype-for-business-server-for-server-maintenance"></a>Impedindo novas conexões com o Skype for Business Server para manutenção de servidor


O Skype for Business Server permite que você leve um servidor offline (por exemplo, para aplicar atualizações de software ou hardware) sem qualquer perda de serviço para os usuários.

Quando você especifica a opção para impedir novas conexões ou chamadas a um servidor em um pool, ele para de aceitar novas conexões e chamadas assim que você implementa essa opção. As novas conexões e chamadas são roteadas através de outros servidores no pool. Um servidor que está impedindo novas conexões permite que suas sessões em conexões existentes continuem até terminarem de modo natural. Quando todas as sessões existentes são concluídas, o servidor está pronto para ser colocado offline.

Quando você impede novas conexões com um Servidor front-end, alguns recursos e serviços do Skype for Business Server dependem do balanceamento de carga DNS para garantir que ele funcione corretamente. Se você não estiver usando o balanceamento de carga DNSno pool, as conexões por meio desses serviços poderão não ser redirecionados para outros servidores durante o período no qual o servidor está impedindo novas conexões e, portanto, quando o servidor é colocado offline, algumas sessões e chamadas podem ser interrompidas. Estes são os recursos que dependem do balanceamento de carga DNS para garantir que esta opção funcione corretamente:

  - Attendant

  - Aplicativo Comunicado de Conferência

  - Aplicativo Grupo de Resposta

  - Aplicativo de comunicado

  - Call Park application

Para obter detalhes sobre o balanceamento de carga DNS, consulte [Requisitos de balanceamento de carga.](../../plan-your-deployment/network-requirements/load-balancing.md)

Além de impedir novas conexões para todos os serviços em um servidor que executa o Skype for Business Server, você também pode impedir novas conexões para serviços individuais do Skype for Business Server. Por exemplo, esse método é útil em uma situação em que você precisa aplicar uma atualização do Skype for Business Server que não exige que todo o servidor seja desligado. Observe que, quando você impede conexões com um serviço, deve selecionar um serviço que é agrupado e exibido na lista de serviços do Windows. Por exemplo, o serviço de Front-End do Skype for Business Server e o agente de coleta de dados para Monitoramento são serviços separados do Skype for Business Server, mas na lista de serviços do Windows eles são consolidados e mostrados como o serviço front-end do Skype for Business Server. Você pode impedir novas conexões para o serviço front-end do Skype for Business Server, mas não pode impedir novas conexões para esses dois serviços individuais subjacentes do Skype for Business Server separadamente.

> [!IMPORTANT]
> Quando você define um servidor para impedir novas conexões e reiniciar o servidor, por padrão, o servidor começa imediatamente a aceitar novas conexões depois de ser inicializado. Para evitar isso, defina o servidor para apenas pausar e reiniciar manualmente antes de reiniciá-lo.

## <a name="to-prevent-new-connections-to-skype-for-business-server"></a>Para impedir novas conexões com o Skype for Business Server

1.  Faça logoff no computador local como membro do grupo Administradores.

2.  Abra o console do snap-in Serviços: **Clique** em Iniciar , aponte para Todos os **Programas,** aponte para Ferramentas Administrativas e clique em **Serviços.**

3.  Na lista, clique duas vezes no serviço Windows do Skype for Business Server para o qual você deseja impedir novas conexões.

4.  Na caixa de diálogo Propriedades, em **Status do serviço: Iniciado,** clique em **Pausar.**

5.  Opcionalmente, mas recomendado, ao lado do tipo **de inicialização,** clique em **Manual**.
    
    > [!IMPORTANT]
    > Quando você define um servidor para impedir novas conexões e reiniciar o servidor, por padrão, o servidor começa imediatamente a aceitar novas conexões depois de ser inicializado. Para evitar isso, defina o servidor para apenas pausar e reiniciar manualmente antes de reiniciá-lo.
