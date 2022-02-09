---
title: Instalar Repositório de Configuração Local
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 4/13/2015
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.dep.DeployMainInstallReplica
ms.prod: skype-for-business-itpro
ms.localizationpriority: medium
ms.assetid: d9c4bcc2-11a7-4d4d-858d-224db217ad32
description: Para começar a instalação de um novo servidor de função Skype for Business Server 2015, você deve primeiro instalar o SQL Server local que hospedará o armazenamento de configuração local. O armazenamento de configuração local atuará como uma réplica somente leitura do Skype for Business Server De gerenciamento central (CMS). Você deve estar conectado ao servidor no qual está executando a etapa Instalar o Repositório de Configuração Local como administrador local no computador e deve ser membro do grupo RTCUniversalServerAdmins ou RTCUniversalGlobalReadOnlyGroup. Se estiver executando a configuração em um Servidor de Borda, não precisará ser um membro do grupo RTCUniversalServerAdmins ou RTCUniversalGlobalReadOnlyGroup. O documento de definição do Construtor de Topologias será lido do documento de definição exportado em vez do armazenamento de Gerenciamento Central. Para exportar o documento de definição do Construtor de Topologias e torná-lo disponível para os Servidores de Borda, consulte o tópico Export Your Topology and Copy It to External Media for Edge Installation.
ms.openlocfilehash: ccbfa553832a7a6f03dba8c88b30f35234efa80f
ms.sourcegitcommit: 59d209ed669c13807e38196dd2a2c0a4127d3621
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/05/2022
ms.locfileid: "62411074"
---
# <a name="install-local-configuration-store"></a>Instalar Repositório de Configuração Local

Para começar a instalação de um novo servidor de função Skype for Business Server 2015, você deve primeiro instalar o SQL Server local que hospedará o armazenamento de configuração local. O armazenamento de configuração local atuará como uma réplica somente leitura do Skype for Business Server De gerenciamento central (CMS). Você deve estar conectado ao servidor no qual está executando a etapa **Instalar o Repositório de Configuração Local** como administrador local no computador e deve ser membro do grupo RTCUniversalServerAdmins ou RTCUniversalGlobalReadOnlyGroup. Se estiver executando a configuração em um Servidor de Borda, não precisará ser um membro do grupo RTCUniversalServerAdmins ou RTCUniversalGlobalReadOnlyGroup. O documento de definição do Construtor de Topologias será lido do documento de definição exportado em vez do armazenamento de Gerenciamento Central. Para exportar o documento de definição do Construtor de Topologias e torná-lo disponível para os Servidores de Borda, consulte o tópico [Export Your Topology and Copy It to External Media for Edge Installation](/previous-versions/office/lync-server-2013/lync-server-2013-export-your-topology-and-copy-it-to-external-media-for-edge-installation).

Para iniciar a instalação:

1. Na página Skype for Business Server 2015, ao lado de **Step1: Install Local Configuration Store**, clique em **Executar**.

2. Na página **Configuração do Servidor Local**, certifique-se de que a opção **Recuperar a configuração automaticamente do Repositório de Gerenciamento Central** esteja selecionada e clique em **Avançar**.

3. Quando a instalação da configuração do servidor local estiver concluída, clique em **Concluir**.

> [!NOTE]
> A instalação do SQL Server local pode levar algum tempo. Você não verá atualizações sobre o andamento na tela de resumo da instalação enquanto SQL Server está sendo instalado. Se você quiser monitorar o andamento da instalação, use o Gerenciador de Tarefas para observar a SQL Server configuração.