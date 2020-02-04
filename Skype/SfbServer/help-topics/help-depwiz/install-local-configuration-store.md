---
title: Instalar Repositório de Configuração Local
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 4/13/2015
audience: ITPro
ms.topic: article
f1.keywords:
- ms.lync.dep.DeployMainInstallReplica
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: d9c4bcc2-11a7-4d4d-858d-224db217ad32
description: Para começar a instalação de um novo servidor de funções do Skype for Business Server 2015, primeiro você deve instalar o SQL Server local que hospedará o repositório de configuração local. O repositório de configuração local atuará como uma réplica somente leitura do CMS (repositório de gerenciamento central) do Skype for Business Server. Você precisa estar conectado ao servidor que está executando a etapa Instalar o Repositório de Configuração Local como o administrador local no computador, e ter associação no grupo RTCUniversalServerAdmins ou RTCUniversalGlobalReadOnlyGroup. Se você estiver executando a configuração em um Servidor de Borda, não precisará ser membro do grupo RTCUniversalServerAdmins ou RTCUniversalGlobalReadOnlyGroup. O documento de definição do construtor de topologias será lido do documento de definição exportado, em vez de do repositório de gerenciamento central. Para exportar o documento de definição do construtor de topologia e disponibilizá-lo para os servidores de borda, consulte o tópico exportar sua topologia e copiá-la para mídia externa para instalação do Edge.
ms.openlocfilehash: 83412bbef1305dab51cbb35ad9044f756154905c
ms.sourcegitcommit: 19f534bfafbc74dbc2d381672b0650a3733cb982
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/03/2020
ms.locfileid: "41687634"
---
# <a name="install-local-configuration-store"></a>Instalar Repositório de Configuração Local

Para começar a instalação de um novo servidor de funções do Skype for Business Server 2015, primeiro você deve instalar o SQL Server local que hospedará o repositório de configuração local. O repositório de configuração local atuará como uma réplica somente leitura do CMS (repositório de gerenciamento central) do Skype for Business Server. Você precisa estar conectado ao servidor que está executando a etapa **Instalar o Repositório de Configuração Local** como o administrador local no computador, e ter associação no grupo RTCUniversalServerAdmins ou RTCUniversalGlobalReadOnlyGroup. Se você estiver executando a configuração em um Servidor de Borda, não precisará ser membro do grupo RTCUniversalServerAdmins ou RTCUniversalGlobalReadOnlyGroup. O documento de definição do construtor de topologias será lido do documento de definição exportado, em vez de do repositório de gerenciamento central. Para exportar o documento de definição do construtor de topologia e disponibilizá-lo para os servidores de borda, consulte o tópico [exportar sua topologia e copiá-la para mídia externa para instalação do Edge](https://technet.microsoft.com/library/def9f416-c519-4a72-b242-7d3057d9c1fd.aspx).

Para começar a instalação:

1. Na página do Skype for Business Server 2015, ao lado de **Step1: instalar o repositório de configuração local**, clique em **executar**.

2. Na página **Configuração do Servidor Local**, certifique-se de que a opção **Recuperar a configuração automaticamente do Repositório de Gerenciamento Central** esteja selecionada e clique em **Avançar**.

3. Quando a instalação da configuração do servidor local estiver concluída, clique em **Concluir**.

> [!NOTE]
> A instalação do SQL Server local pode demorar algum tempo. Você não verá atualizações em andamento na tela Resumo da instalação enquanto o SQL Server estiver sendo instalado. Se você quiser monitorar o andamento da instalação, use o Gerenciador de tarefas para assistir à configuração do SQL Server.


