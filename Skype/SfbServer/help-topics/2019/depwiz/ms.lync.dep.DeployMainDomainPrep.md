---
title: Preparar Domínio Atual
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.dep.DeployMainDomainPrep
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: bfcb37ca-34eb-4d0d-9694-6edd2e7fe0f3
ROBOTS: NOINDEX, NOFOLLOW
description: 'Para preparar um domínio para servidores host que executam o Skype for Business Server ou usuários do Skype for Business Server, você deve concluir a etapa 5: preparar o domínio atual, conforme descrito no tópico usando a configuração para executar a preparação do domínio. Para completar a etapa, é necessário estar conectado como membro do grupo Administradores de Domínio no domínio que você está preparando ou como membro do grupo Administradores de Empresa da floresta a qual o domínio pertence. Para preparar o domínio:'
ms.openlocfilehash: 16b47a211ebff577844cdc29b6e28acd00952d20
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34303430"
---
# <a name="prepare-current-domain"></a>Preparar Domínio Atual

Para preparar um domínio para servidores host que executam o Skype for Business Server ou usuários do Skype for Business Server, você deve concluir a **etapa 5: preparar o domínio atual**, conforme descrito no tópico [usando a configuração para executar a preparação do domínio](https://technet.microsoft.com/library/95dab800-1f2c-4506-b36c-99986643b149.aspx). Para completar a etapa, é necessário estar conectado como membro do grupo Administradores de Domínio no domínio que você está preparando ou como membro do grupo Administradores de Empresa da floresta a qual o domínio pertence. Para preparar o domínio:

1. Na pasta de instalação ou mídia do Skype for Business Server, execute Setup. exe para iniciar o assistente de implantação do Skype for Business Server.

2. Clique em **Preparar o Active Directory** e espere que o estado da implantação seja determinado.

3. Na **Etapa 5: preparar o domínio atual**, clique em **Executar**.

4. Na página **Executando Comandos**, procure **Status da tarefa: Concluída** e clique em **Exibir Log**.

5. Na coluna **ação** , expanda o **domínio Prep**, procure um ** \<resultado\> ** de execução de sucesso no final de cada tarefa para verificar se a preparação do domínio foi concluída com êxito, feche o log e clique em **concluir**.

> [!TIP]
> Se precisar examinar os arquivos de log criados pelo assistente de implantação do Skype for Business Server, você poderá encontrá-los no computador em que o assistente de implantação foi executado no diretório de usuários do usuário dos serviços de domínio Active Directory que executou a etapa. Por exemplo, se o usuário tiver entrado como administrador do domínio no domínio Contoso.net, os arquivos de log serão localizados em: C:\Users\Administrator.Contoso\AppData\Local\Temp.


