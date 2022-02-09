---
title: Adicionar Servidor de Borda
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/25/2015
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.AddEdgeServerPage
ms.prod: skype-for-business-itpro
ms.localizationpriority: medium
ms.assetid: 9bd9c2b2-8329-4b31-a937-e462f5cc7293
description: Para incorporar um Servidor de Borda ou um pool de Servidor de Borda em seu design de topologia, é necessário especificar o nome de domínio totalmente qualificado (FQDN) do servidor no qual você deseja implantar o Servidor de Borda ou o pool de Servidores de Borda. Antes de publicar uma topologia que inclua o pool de Servidor de Borda ou Servidor de Borda e a instalação Skype for Business Server, você deve ter concluído todos os pré-requisitos para implantar o acesso de usuário externo. Para obter detalhes sobre esses pré-requisitos, consulte Preparing for Installation of Servers in the Perimeter Network, na documentação de Implantação.
ms.openlocfilehash: 40a30f55a04bb4520fc136d3301eaa54ef16e1a0
ms.sourcegitcommit: 59d209ed669c13807e38196dd2a2c0a4127d3621
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/05/2022
ms.locfileid: "62416714"
---
# <a name="add-edge-server"></a>Adicionar Servidor de Borda

Para incorporar um Servidor de Borda ou um pool de Servidor de Borda em seu design de topologia, é necessário especificar o nome de domínio totalmente qualificado (FQDN) do servidor no qual você deseja implantar o Servidor de Borda ou o pool de Servidores de Borda. Antes de publicar uma topologia que inclua o pool de Servidor de Borda ou Servidor de Borda e a instalação Skype for Business Server, você deve ter concluído todos os pré-requisitos para implantar o acesso de usuário externo. Para obter detalhes sobre esses pré-requisitos, consulte [Preparing for Installation of Servers in the Perimeter Network](/previous-versions/office/lync-server-2013/lync-server-2013-preparing-for-installation-of-servers-in-the-perimeter-network) na documentação de Implantação.

> [!IMPORTANT]
> O nome especificado por você precisa ser idêntico ao nome de computador configurado no servidor. Por padrão, o nome de computador de um computador que não faz parte de um domínio é um nome curto, não um FQDN. O Construtor de Topologia usa FQDNs, não nomes curtos. É necessário configurar um sufixo DNS (Domain Name System) no nome do computador a ser implantado como um Servidor de Borda ou pool de Servidores de Borda que não faz parte de um domínio.

> [!TIP]
> Caso planeje implementar um pool de Servidor de Borda no futuro, selecione **Pool de múltiplos computadores**. Embora um pool seja definido como dois ou mais computadores que estão com cargas balanceadas, você pode criar um pool de único computador e criar um pool FQDN para o computador único. Quando você estiver pronto para adicionar mais computadores ao pool posteriormente, você deve definir novamente o Construtor de Topologias para definir o novo membro do pool, publicar a nova topologia e configurar o novo membro do pool do Servidor de Borda por meio do Assistente de Implantação do Skype for Business Server. Você também deve adicionar o novo membro do pool aos balanceadores de carga do pool, balanceamento de carga DNS ou balanceadores de carga de hardware apropriados. A interface de Borda interna e a interface de Borda externa devem utilizar o mesmo tipo de balanceamento de carga. Você não pode usar o balanceamento de carga DNS em uma interface de Borda e balanceamento de carga de hardware na outra interface de borda. Assegure-se de que você está adicionando o novo servidor membro para o balanceador de carga adequado.

É possível adicionar suporte para acesso a usuário externo quando você implanta sua topologia inicial, ou depois de implantar sua topologia inicial. Para obter detalhes sobre como adicionar Servidores de Borda ou pool de Servidores de Borda a uma topologia existente, consulte [Define Your Edge Topology](/previous-versions/office/lync-server-2013/lync-server-2013-define-your-edge-topology) na documentação de Implantação do Servidor de Borda.