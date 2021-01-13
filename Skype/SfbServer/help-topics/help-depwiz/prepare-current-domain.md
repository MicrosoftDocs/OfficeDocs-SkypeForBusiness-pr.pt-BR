---
title: Preparar Domínio Atual
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 2/8/2018
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.dep.DeployMainDomainPrep
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: bfcb37ca-34eb-4d0d-9694-6edd2e7fe0f3
description: 'Para preparar um domínio para hospedar servidores executando os usuários do Skype for Business Server 2015 ou do Skype for Business Server, você deve concluir a Etapa 5: Preparar o Domínio Atual, conforme descrito no tópico Using Setup to Run Domain Preparation. Para concluir a etapa, você deve estar conectado como membro do grupo Administradores de Domínio no domínio que você está preparando ou como membro do grupo Administradores de Empresa da floresta à que o domínio pertence. Para preparar o domínio:'
ms.openlocfilehash: b43af552983a5a7aae998fab6de9ace4e96084b2
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49804956"
---
# <a name="prepare-current-domain"></a>Preparar Domínio Atual

Para preparar um domínio para hospedar servidores executando os usuários do Skype for Business Server 2015 ou do Skype for Business Server, você deve concluir a Etapa **5:** Preparar Domínio Atual, conforme descrito no tópico Using [Setup to Run Domain Preparation](https://technet.microsoft.com/library/95dab800-1f2c-4506-b36c-99986643b149.aspx). Para concluir a etapa, você deve estar conectado como membro do grupo Administradores de Domínio no domínio que você está preparando ou como membro do grupo Administradores de Empresa da floresta à que o domínio pertence. Para preparar o domínio:

1. Na pasta ou mídia de instalação do Skype for Business Server 2015, execute o Setup.exe para iniciar o Assistente de Implantação do Skype for Business Server.

2. Clique em **Preparar Active Directory** e aguarde o estado de implantação ser determinado.

3. Na **Etapa 5: Preparar o Domínio Atual**, clique em **Executar**.

4. Na página **Executando Comandos**, procure por **Status da tarefa: concluída** e clique em **Exibir Log**.

5. Na coluna **Ação,** expanda **o Domain Prep**, procure um Resultado de Execução no final de cada tarefa para verificar se a preparação do domínio foi concluída com êxito, feche o log e clique em **\<Success\>** **Concluir.**

> [!TIP]
> Se precisar revisar os arquivos de log criados pelo Assistente de Implantação do Skype for Business Server, você poderá encontrá-los no computador onde o Assistente de Implantação foi executado no diretório Usuários do usuário dos Serviços de Domínio Active Directory que executaram a etapa. Por exemplo, se o usuário fez logon como administrador de domínio no domínio Contoso.net, os arquivos de log estão localizados em: C:\Users\Administrator.Contoso\AppData\Local\Temp.


