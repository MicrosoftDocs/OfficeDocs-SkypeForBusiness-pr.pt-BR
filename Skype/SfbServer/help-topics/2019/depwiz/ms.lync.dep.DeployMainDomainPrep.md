---
title: Preparar Domínio Atual
ms.reviewer: ''
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.dep.DeployMainDomainPrep
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: bfcb37ca-34eb-4d0d-9694-6edd2e7fe0f3
ROBOTS: NOINDEX, NOFOLLOW
description: 'Para preparar um domínio para servidores de host executando Skype para Business Server ou Skype para usuários Business Server, você deve concluir a etapa 5: Preparar domínio atual, conforme descrito no tópico usando o Setup para executar a preparação do domínio. Para completar a etapa, é necessário estar conectado como membro do grupo Administradores de Domínio no domínio que você está preparando ou como membro do grupo Administradores de Empresa da floresta a qual o domínio pertence. Para preparar o domínio:'
ms.openlocfilehash: 0544381fbb4965bd370f1ac128d2e203de0cb109
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/23/2019
ms.locfileid: "32216169"
---
# <a name="prepare-current-domain"></a>Preparar Domínio Atual

Para preparar um domínio para servidores de host executando Skype para Business Server ou Skype para usuários Business Server, você deve concluir **etapa 5: Preparar domínio atual**, conforme descrito no tópico [Usando o Setup para executar a preparação do domínio](https://technet.microsoft.com/library/95dab800-1f2c-4506-b36c-99986643b149.aspx). Para completar a etapa, é necessário estar conectado como membro do grupo Administradores de Domínio no domínio que você está preparando ou como membro do grupo Administradores de Empresa da floresta a qual o domínio pertence. Para preparar o domínio:

1. A partir do Skype para a pasta de instalação do servidor de negócios ou mídia, execute Setup.exe para iniciar o Skype para o Assistente de implantação de servidor de negócios.

2. Clique em **Preparar o Active Directory** e espere que o estado da implantação seja determinado.

3. Na **Etapa 5: preparar o domínio atual**, clique em **Executar**.

4. Na página **Executando Comandos**, procure **Status da tarefa: Concluída** e clique em **Exibir Log**.

5. Na coluna **ação** , expanda o **Domínio Prep**, procure uma ** \<sucesso\> ** resultado da execução do final de cada tarefa para verificar que a preparação do domínio foi concluída com êxito, feche o log e clique em **Concluir**.

> [!TIP]
> Se você precisar revisar os arquivos de log são criados pelo Skype para o Assistente de implantação de servidor de negócios, você pode encontrá-los no computador onde o Assistente de implantação foi executado no diretório de usuários do usuário Active Directory Domain Services que executou a etapa. Por exemplo, se o usuário logado como administrador de domínio no domínio Contoso.net, os arquivos de log estão localizados em: C:\Users\Administrator.Contoso\AppData\Local\Temp.


