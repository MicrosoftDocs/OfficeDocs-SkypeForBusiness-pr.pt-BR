---
title: Preparar Domínio Atual
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.custom:
- ms.lync.dep.DeployMainDomainPrep
ms.prod: skype-for-business-itpro
f1.keywords:
- CSH
localization_priority: Normal
ms.assetid: bfcb37ca-34eb-4d0d-9694-6edd2e7fe0f3
ROBOTS: NOINDEX, NOFOLLOW
description: 'Para preparar um domínio para hospedar servidores que executam usuários do Skype for Business Server ou do Skype for Business Server, você deve concluir a Etapa 5: Preparar o Domínio Atual, conforme descrito no tópico Using Setup to Run Domain Preparation. Para concluir a etapa, você deve estar conectado como membro do grupo Administradores de Domínio no domínio que você está preparando ou como membro do grupo Administradores corporativos da floresta à que o domínio pertence. Para preparar o domínio:'
ms.openlocfilehash: a71e50b0f3d55709c3c22709177b41e541f7075f
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51097333"
---
# <a name="prepare-current-domain"></a>Preparar Domínio Atual

Para preparar um domínio para hospedar servidores executando usuários do Skype for Business Server ou do Skype for Business Server, você deve concluir a Etapa **5:** Preparar o Domínio Atual , conforme descrito no tópico [Using Setup to Run Domain Preparation](/previous-versions/office/lync-server-2013/lync-server-2013-running-domain-preparation). Para concluir a etapa, você deve estar conectado como membro do grupo Administradores de Domínio no domínio que você está preparando ou como membro do grupo Administradores corporativos da floresta à que o domínio pertence. Para preparar o domínio:

1. Na pasta ou mídia de instalação do Skype for Business Server, execute Setup.exe para iniciar o Assistente de Implantação do Skype for Business Server.

2. Clique em **Preparar Active Directory** e aguarde o estado de implantação ser determinado.

3. Na **Etapa 5: Preparar o Domínio Atual**, clique em **Executar**.

4. Na página **Executando Comandos**, procure por **Status da tarefa: concluída** e clique em **Exibir Log**.

5. Na coluna **Ação,** expanda **Preparação** de Domínio , procure um Resultado de Execução no final de cada tarefa para verificar se a preparação do domínio foi concluída com êxito, feche o log e clique em **\<Success\>** **Concluir**.

> [!TIP]
> Se você precisar revisar os arquivos de log criados pelo Assistente de Implantação do Skype for Business Server, poderá encontrá-los no computador onde o Assistente de Implantação foi executado no diretório Usuários do usuário dos Serviços de Domínio do Active Directory que executaram a etapa. Por exemplo, se o usuário fez logon como administrador de domínio no domínio Contoso.net, os arquivos de log estão localizados em: C:\Users\Administrator.Contoso\AppData\Local\Temp.