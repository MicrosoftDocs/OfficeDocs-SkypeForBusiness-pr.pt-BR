---
title: Adicionar Servidor de Borda
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 3/25/2015
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.AddEdgeServerPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 9bd9c2b2-8329-4b31-a937-e462f5cc7293
description: Para incorporar um Servidor de Borda ou um pool de Servidor de Borda em seu design de topologia, é necessário especificar o nome de domínio totalmente qualificado (FQDN) do servidor no qual você deseja implantar o Servidor de Borda ou o pool de Servidores de Borda. Antes de publicar uma topologia que inclua o Servidor de Borda ou pool de Servidores de Borda e instalar o Skype for Business Server, você deve ter concluído todos os pré-requisitos para implantar o acesso de usuário externo. Para obter detalhes sobre esses pré-requisitos, consulte Preparing for Installation of Servers in the Perimeter Network, na documentação de Implantação.
ms.openlocfilehash: fb5fc4f34531da9bae4585d5a6140fdfe5837735
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49803591"
---
# <a name="add-edge-server"></a>Adicionar Servidor de Borda

Para incorporar um Servidor de Borda ou um pool de Servidor de Borda em seu design de topologia, é necessário especificar o nome de domínio totalmente qualificado (FQDN) do servidor no qual você deseja implantar o Servidor de Borda ou o pool de Servidores de Borda. Antes de publicar uma topologia que inclua o Servidor de Borda ou pool de Servidores de Borda e instalar o Skype for Business Server, você deve ter concluído todos os pré-requisitos para implantar o acesso de usuário externo. Para obter detalhes sobre esses pré-requisitos, consulte [Preparing for Installation of Servers in the Perimeter Network](https://technet.microsoft.com/library/5e6c457a-f964-4ef7-a709-97abda9c673a.aspx) na documentação de Implantação.

> [!IMPORTANT]
> O nome especificado por você precisa ser idêntico ao nome de computador configurado no servidor. Por padrão, o nome de computador de um computador que não faz parte de um domínio é um nome curto, não um FQDN. O Construtor de Topologia usa FQDNs, não nomes curtos. É necessário configurar um sufixo DNS (Domain Name System) no nome do computador a ser implantado como um Servidor de Borda ou pool de Servidores de Borda que não faz parte de um domínio.

> [!TIP]
> Caso planeje implementar um pool de Servidor de Borda no futuro, selecione **Pool de múltiplos computadores**. Embora um pool seja definido como dois ou mais computadores que estão com cargas balanceadas, você pode criar um pool de único computador e criar um pool FQDN para o computador único. Quando estiver pronto para adicionar mais computadores ao pool mais tarde, você deverá definir o Construtor de Topologias novamente para definir o novo membro do pool, publicar a nova topologia e configurar o novo membro do pool do Servidor de Borda por meio do Assistente de Implantação do Skype for Business Server. Você também deve adicionar o novo membro do pool aos balanceadores de carga do pool, balanceamento de carga DNS ou balanceadores de carga de hardware apropriados. A interface de Borda interna e a interface de Borda externa devem utilizar o mesmo tipo de balanceamento de carga. Você não pode usar o balanceamento de carga DNS em uma interface de Borda e balanceamento de carga de hardware na outra interface de borda. Certifique-se de que você está adicionando o novo servidor membro ao balanceador de carga apropriado.

É possível adicionar suporte para acesso a usuário externo quando você implanta sua topologia inicial, ou depois de implantar sua topologia inicial. Para obter detalhes sobre como adicionar Servidores de Borda ou pool de Servidores de Borda a uma topologia existente, consulte [Define Your Edge Topology](https://technet.microsoft.com/library/787b23f1-8fa0-4c37-abf2-c516c5dd66f0.aspx) na documentação de Implantação do Servidor de Borda.


