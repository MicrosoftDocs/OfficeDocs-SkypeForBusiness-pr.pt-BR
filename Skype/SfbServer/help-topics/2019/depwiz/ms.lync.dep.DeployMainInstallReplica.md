---
title: Instalar Repositório de Configuração Local
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.custom:
- ms.lync.dep.DeployMainInstallReplica
ms.prod: skype-for-business-itpro
f1.keywords:
- CSH
localization_priority: Normal
ms.assetid: d9c4bcc2-11a7-4d4d-858d-224db217ad32
ROBOTS: NOINDEX, NOFOLLOW
description: Para iniciar a instalação de um novo servidor de função do Skype for Business Server, você deve primeiro instalar o SQL Server local que hospedará o armazenamento de configuração local. O armazenamento de configuração local atuará como uma réplica somente leitura do CmS (armazenamento de Gerenciamento Central) do Skype for Business Server.
ms.openlocfilehash: dcaf00e0bd14daecb6d2859bf40463265a3d6bc6
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49833801"
---
# <a name="install-local-configuration-store"></a>Instalar Repositório de Configuração Local

Para iniciar a instalação de um novo servidor de função do Skype for Business Server, você deve primeiro instalar o SQL Server local que hospedará o armazenamento de configuração local. O armazenamento de configuração local atuará como uma réplica somente leitura do CmS (armazenamento de Gerenciamento Central) do Skype for Business Server. Você deve estar conectado ao servidor no qual está executando a etapa **Instalar o Repositório de Configuração Local** como administrador local no computador e deve ser membro do grupo RTCUniversalServerAdmins ou RTCUniversalGlobalReadOnlyGroup. Se estiver executando a configuração em um Servidor de Borda, não precisará ser um membro do grupo RTCUniversalServerAdmins ou RTCUniversalGlobalReadOnlyGroup. O documento de definição do Construtor de Topologias será lido do documento de definição exportado em vez do armazenamento de Gerenciamento Central. Para exportar o documento de definição do Construtor de Topologias e torná-lo disponível para os Servidores de Borda, consulte o tópico[Export Your Topology and Copy It to External Media for Edge Installation](https://technet.microsoft.com/library/def9f416-c519-4a72-b242-7d3057d9c1fd.aspx).

Para iniciar a instalação:

1. Na página Skype for Business Server, ao lado de **Step1: Install Local Configuration Store**, clique em **Executar**.

2. Na página **Configuração do Servidor Local**, certifique-se de que a opção **Recuperar a configuração automaticamente do Repositório de Gerenciamento Central** esteja selecionada e clique em **Avançar**.

3. Quando a instalação da configuração do servidor local estiver concluída, clique em **Concluir**.

> [!NOTE]
> A instalação do SQL Server local pode levar algum tempo. Você não verá atualizações sobre o progresso na tela de resumo da instalação enquanto o SQL Server estiver sendo instalado. Se você quiser monitorar o progresso da instalação, use o Gerenciador de Tarefas para observar a configuração do SQL Server.


