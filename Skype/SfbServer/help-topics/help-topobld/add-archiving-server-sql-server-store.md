---
title: Adicionar Repositório de Servidor SQL para Servidor de Arquivamento
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/8/2018
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.AddArchivingServerSqlStorePage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 26e0a748-e31d-4c66-b225-b37e0a45408f
description: O servidor de arquivamento requer uma edição de 64 bits com suporte do software de banco de dados do SQL Server para armazenar os dados de arquivo morto. Você pode selecionar um banco de dados do SQL Server definido anteriormente para ser usado para arquivamento ou definir um novo banco de dados do SQL Server especificando um FQDN (nome de domínio totalmente qualificado) do servidor no qual o banco de dados do SQL Server residirá e a instância do SQL Server que você deseja usar para o novo banco de dados do SQL Server (que pode ser a instância padrão ou uma instância nomeada que você especificar).
ms.openlocfilehash: eb25152916c61ff40274705a408fe0a7a618cbcc
ms.sourcegitcommit: c69ab11b701a4833179b8479bc3204dfd4412096
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/23/2020
ms.locfileid: "48217432"
---
# <a name="add-archiving-server-sql-server-store"></a>Adicionar Repositório de Servidor SQL para Servidor de Arquivamento

O servidor de arquivamento requer uma edição de 64 bits com suporte do software de banco de dados do SQL Server para armazenar os dados de arquivo morto. Você pode selecionar um banco de dados do SQL Server definido anteriormente para ser usado para arquivamento ou definir um novo banco de dados do SQL Server especificando um FQDN (nome de domínio totalmente qualificado) do servidor no qual o banco de dados do SQL Server residirá e a instância do SQL Server que você deseja usar para o novo banco de dados do SQL Server (que pode ser a instância padrão ou uma instância nomeada que você especificar).

> [!NOTE]
> Se a conta usada para publicar a topologia tiver os direitos de usuário e permissões apropriadas, será possível criar o banco de dados de arquivamento (LcsLog) ao publicar sua topologia. Também é possível criar o banco de dados posteriormente, como parte do procedimento de instalação, ou de outra forma.

> [!NOTE]
> Para instalar e implantar os bancos de dados no servidor baseado em SQL Server para arquivamento, você deve ser membro do grupo sysadmins do SQL Server para o servidor baseado em SQL Server no qual você está instalando os arquivos de banco de dados. Se você não for um membro do grupo sysadmins do SQL Server, deverá solicitar a adição ao grupo até que os arquivos do banco de dados sejam implantados. Se você não puder se tornar um membro do grupo sysadmins, forneça o script para configurar e implantar os bancos de dados do SQL Server. Para obter detalhes sobre os direitos e permissões de usuário necessários para realizar os procedimentos, consulte [Deployment Permissions for SQL Server](https://technet.microsoft.com/library/56ea0c02-bcf5-4d45-aa13-570531c29074.aspx) na documentação Implantação.


