---
title: Preparar Domínio Atual
ms.reviewer: null
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 2/8/2018
audience: ITPro
ms.topic: article
f1.keywords:
  - CSH
ms.custom:
  - ms.lync.dep.DeployMainDomainPrep
ms.prod: skype-for-business-itpro
ms.localizationpriority: medium
ms.assetid: bfcb37ca-34eb-4d0d-9694-6edd2e7fe0f3
description: 'Para preparar um domínio para hospedar servidores executando Skype for Business Server 2015 ou Skype for Business Server usuários, você deve concluir a Etapa 5: Preparar o Domínio Atual, conforme descrito no tópico Using Setup to Run Domain Preparation. Para concluir a etapa, você deve estar conectado como membro do grupo Administradores de Domínio no domínio que você está preparando ou como membro do grupo administradores do Enterprise da floresta à que o domínio pertence. Para preparar o domínio:'
---

# <a name="prepare-current-domain"></a>Preparar Domínio Atual

Para preparar um domínio para hospedar servidores que executam o Skype for Business Server 2015 ou Skype for Business Server usuários, você deve concluir a Etapa **5: Preparar** o Domínio Atual, conforme descrito no tópico [Using Setup to Run Domain Preparation](/previous-versions/office/lync-server-2013/lync-server-2013-running-domain-preparation). Para concluir a etapa, você deve estar conectado como membro do grupo Administradores de Domínio no domínio que você está preparando ou como membro do grupo administradores do Enterprise da floresta à que o domínio pertence. Para preparar o domínio:

1. Na pasta Skype for Business Server ou mídia de instalação do 2015, execute Setup.exe para iniciar o Assistente de Implantação Skype for Business Server.

2. Clique em **Preparar Active Directory** e aguarde o estado de implantação ser determinado.

3. Na **Etapa 5: Preparar o Domínio Atual**, clique em **Executar**.

4. Na página **Executando Comandos**, procure por **Status da tarefa: concluída** e clique em **Exibir Log**.

5. Na coluna **Ação** , expanda **a** Preparação de Domínio, procure um Resultado de Execução no final de cada tarefa para verificar se a **\<Success\>** preparação do domínio foi concluída com êxito, feche o log e clique em **Concluir**.

> [!TIP]
> Se você precisar revisar os arquivos de log criados pelo Assistente de Implantação do Skype for Business Server, você poderá encontrá-los no computador onde o Assistente de Implantação foi executado no diretório Usuários do usuário dos Serviços de Domínio active Directory que executaram a etapa. Por exemplo, se o usuário fez logon como administrador de domínio no domínio Contoso.net, os arquivos de log estão localizados em: C:\Users\Administrator.Contoso\AppData\Local\Temp.