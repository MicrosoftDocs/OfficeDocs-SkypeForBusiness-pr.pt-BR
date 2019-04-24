---
title: Adicionar Servidor de Borda
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.AddEdgeServerPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 9bd9c2b2-8329-4b31-a937-e462f5cc7293
ROBOTS: NOINDEX, NOFOLLOW
description: Para incorporar um Servidor de Borda ou um pool de Servidor de Borda em seu design de topologia, é necessário especificar o nome de domínio totalmente qualificado (FQDN) do servidor no qual você deseja implantar o Servidor de Borda ou o pool de Servidor de Borda. Antes de publicar uma topologia que inclui o servidor de borda ou pool de servidor de borda e instalando Skype para Business Server, você deve ter concluído a todos os pré-requisitos para a implantação de acesso de usuário externo. Para obter detalhes sobre esses pré-requisitos, consulte Preparing for Installation of Servers in the Perimeter Network na documentação Implantação.
ms.openlocfilehash: e54deff6c6dcf371ba86f3fbfa1b974489cb3f11
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/23/2019
ms.locfileid: "32202114"
---
# <a name="add-edge-server"></a>Adicionar Servidor de Borda

Para incorporar um Servidor de Borda ou um pool de Servidor de Borda em seu design de topologia, é necessário especificar o nome de domínio totalmente qualificado (FQDN) do servidor no qual você deseja implantar o Servidor de Borda ou o pool de Servidor de Borda. Antes de publicar uma topologia que inclui o servidor de borda ou pool de servidor de borda e instalando Skype para Business Server, você deve ter concluído a todos os pré-requisitos para a implantação de acesso de usuário externo. Para obter detalhes sobre esses pré-requisitos, consulte [Preparing for Installation of Servers in the Perimeter Network](https://technet.microsoft.com/library/5e6c457a-f964-4ef7-a709-97abda9c673a.aspx) na documentação Implantação.

> [!IMPORTANT]
> O nome que você especificar dever ser idêntico ao nome de computador configurado no servidor. Por padrão, o nome de computador de um computador que não faz parte de um domínio é um nome curto, não um FQDN. O Construtor de Topologias usa FQDNs, não nomes curtos. É necessário configurar um sufixo DNS (Sistema de Nomes de Domínio) no nome do computador a ser implantado como um Servidor de Borda ou pool de Servidor de Borda que não faz parte de um domínio.

> [!TIP]
> Se você planeja implementar um pool de Servidor de Borda no futuro, selecione **Pool de vários computadores**. Embora um pool seja definido como dois ou mais computadores com carga balanceada, é possível criar um único pool de computadores e criar um FQDN de pool para o computador único. Quando você estiver pronto para adicionar mais computadores ao pool posteriormente, você deve ser o construtor de topologia novamente para definir o novo membro do pool, publicar a nova topologia e configurar o novo membro de pool do servidor de borda através do Skype para o Assistente de implantação de servidor de negócios. Também é necessário adicionar o novo membro do pool aos balanceadores de carga apropriados ao pool, balanceamento de carga DNS ou balanceadores de carga de hardware. As interfaces de Borda interna e externa precisam usar o mesmo tipo de balanceamento de carga. Não é possível usar balanceamento de carga DNS em uma interface de Borda e balanceamento de carga de hardware na outra interface de Borda. Verifique se o novo servidor membro foi adicionado ao balanceador de carga apropriado.

É possível adicionar suporte para o acesso de usuário externo quando você implanta sua topologia inicial ou depois de implantar sua topologia inicial. Para obter detalhes sobre como adicionar Servidores de Borda ou pool de Servidor de Borda a uma topologia existente, consulte [Define Your Edge Topology](https://technet.microsoft.com/library/787b23f1-8fa0-4c37-abf2-c516c5dd66f0.aspx) na documentação Implantação do Servidor de Borda.


