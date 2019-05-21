---
title: Como impedir novas conexões
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: ''
ms.openlocfilehash: b7aa303f2b49a806434af91789ab3e610fdc45c0
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34279484"
---
# <a name="preventing-new-connections-to-skype-for-business-server-for-server-maintenance"></a>Como impedir novas conexões com o Skype for Business Server para manutenção do servidor


O Skype for Business Server permite que você coloque um servidor offline (por exemplo, para aplicar atualizações de software ou hardware) sem perda de serviço aos usuários.

Quando você especificar a opção para impedir novas conexões ou chamadas para um servidor em um pool, ela deixará de fazer novas conexões e chamadas assim que você implementar essa opção. Essas novas conexões e chamadas são roteadas por meio de outros servidores no pool. Um servidor que está impedindo novas conexões permite que suas sessões em conexões existentes continuem até que elas terminem naturalmente. Quando todas as sessões existentes terminarem, o servidor estará pronto para ser colocado offline.

Quando você impede novas conexões a um servidor front-end, alguns serviços e recursos do Skype for Business Server dependem do balanceamento de carga de DNS para garantir que funcionem corretamente. Se você não estiver usando o balanceamento de carga de DNS no pool, as conexões por meio desses serviços não poderão ser reencaminhadas a outros servidores durante o período em que o servidor está impedindo novas conexões e, portanto, quando o servidor for colocado offline, algumas sessões e chamadas poderão ser interrompido. Os recursos que dependem do balanceamento de carga de DNS para garantir que essa opção funcione corretamente são os seguintes:

  - Atendedor

  - Aplicativo Comunicado de Conferência

  - Aplicativo Grupo de Resposta

  - Aplicativo Comunicado

  - Aplicativo de Estacionamento de Chamada

Para obter detalhes sobre o balanceamento de carga de DNS, consulte [requisitos de balanceamento de carga](../../plan-your-deployment/network-requirements/load-balancing.md).

Além de impedir novas conexões para todos os serviços em um servidor que executa o Skype for Business Server, você também pode impedir novas conexões para serviços individuais do Skype for Business Server. Por exemplo, esse método é útil em uma situação em que você precisa aplicar uma atualização do Skype for Business Server que não exija que todo o servidor seja desligado. Observe que, ao impedir conexões para um serviço, você deve selecionar um serviço como ele está agrupado e exibido na lista de serviços do Windows. Por exemplo, o serviço de front-end do Skype for Business Server e o agente de coleta de dados para monitoração são serviços do Skype for Business Server separados, mas na lista de serviços do Windows eles são consolidados e exibidos como front-end do Skype for Business Server atender. Você pode impedir novas conexões para o serviço de front-end do Skype for Business Server, mas não pode impedir novas conexões para esses dois serviços individuais subjacentes do Skype for Business Server separadamente.

> [!IMPORTANT]
> Quando você define um servidor para impedir novas conexões e, em seguida, reiniciar o servidor, por padrão, o servidor começará imediatamente a aceitar novas conexões depois que ele for iniciado. Para evitar isso, defina o servidor para pausar e retomar manualmente, antes de reiniciar o servidor.

## <a name="to-prevent-new-connections-to-skype-for-business-server"></a>Para impedir novas conexões com o Skype for Business Server

1.  Faça logon no computador local como membro do grupo Administradores.

2.  Abra o console do snap-in Serviços: clique em **Iniciar**, aponte para **todos os programas**, aponte para **Ferramentas administrativas**e clique em **Serviços**.

3.  Na lista, clique duas vezes no serviço do Windows do Skype for Business Server ao qual você deseja impedir novas conexões.

4.  Na caixa de diálogo Propriedades, em **status do serviço: iniciado**, **** clique em Pausar.

5.  Opcionalmente, mas recomendado, ao lado de **tipo de inicialização**, clique em **manual**.
    
    > [!IMPORTANT]
    > Quando você define um servidor para impedir novas conexões e, em seguida, reiniciar o servidor, por padrão, o servidor começará imediatamente a aceitar novas conexões depois que ele for iniciado. Para evitar isso, defina o servidor para pausar e retomar manualmente, antes de reiniciar o servidor.
