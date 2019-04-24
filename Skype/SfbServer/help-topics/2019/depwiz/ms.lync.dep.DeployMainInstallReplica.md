---
title: Instalar Repositório de Configuração Local
ms.reviewer: ''
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.dep.DeployMainInstallReplica
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: d9c4bcc2-11a7-4d4d-858d-224db217ad32
ROBOTS: NOINDEX, NOFOLLOW
description: Para iniciar a instalação de um novo Skype para o servidor de função de servidor de negócios, você deve instalar primeiro o servidor local de SQL que hospedará o repositório de configuração local. O repositório de configuração local irão agir como uma réplica somente leitura do Skype para o repositório de gerenciamento Central do Business Server (CMS).
ms.openlocfilehash: 5030cb426582ca849b01cea7995401eca276021c
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/23/2019
ms.locfileid: "32216127"
---
# <a name="install-local-configuration-store"></a>Instalar Repositório de Configuração Local

Para iniciar a instalação de um novo Skype para o servidor de função de servidor de negócios, você deve instalar primeiro o servidor local de SQL que hospedará o repositório de configuração local. O repositório de configuração local irão agir como uma réplica somente leitura do Skype para o repositório de gerenciamento Central do Business Server (CMS). Você precisa estar conectado ao servidor que está executando a etapa **Instalar o Repositório de Configuração Local** como o administrador local no computador, e ter associação no grupo RTCUniversalServerAdmins ou RTCUniversalGlobalReadOnlyGroup. Se você estiver executando a configuração em um Servidor de Borda, não precisará ser membro do grupo RTCUniversalServerAdmins ou RTCUniversalGlobalReadOnlyGroup. O documento de definição do construtor de topologia serão lidas do documento em vez de definição exportada do repositório de gerenciamento Central. Para exportar o documento de definição do construtor de topologias e disponibilizá-lo aos servidores de borda, consulte o tópico[Exportar Your Topology and Copy-la na mídia externa para instalação de borda](https://technet.microsoft.com/library/def9f416-c519-4a72-b242-7d3057d9c1fd.aspx).

Para começar a instalação:

1. Sobre o Skype para página Business Server, ao lado de **etapa 1: instalar repositório de configuração Local**, clique em **Executar**.

2. Na página **Configuração do Servidor Local**, certifique-se de que a opção **Recuperar a configuração automaticamente do Repositório de Gerenciamento Central** esteja selecionada e clique em **Avançar**.

3. Quando a instalação da configuração do servidor local estiver concluída, clique em **Concluir**.

> [!NOTE]
> A instalação do SQL Server local pode levar algum tempo. Você não verá as atualizações em progresso na tela se resumo instalação enquanto o SQL Server está sendo instalado. Se você deseja monitorar o progresso da instalação, use o Gerenciador de tarefas para assistir a instalação do SQL Server.


