---
title: Adicionar Repositório de Servidor SQL para Servidor de Arquivamento
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
- ms.lync.tb.AddArchivingServerSqlStorePage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 26e0a748-e31d-4c66-b225-b37e0a45408f
description: O Servidor de Arquivamento requer uma edição de 64 bits suportada do software de banco de dados do SQL Server para armazenar os dados de arquivo morto. Você pode selecionar um banco de dados do SQL Server definido anteriormente a ser usado para arquivamento ou definir um novo banco de dados do SQL Server especificando um FQDN (nome de domínio totalmente qualificado) do servidor no qual o banco de dados do SQL Server irá residir e a instância do SQL Server que você deseja usar para o novo banco de dados do SQL Server (que pode ser a instância padrão ou uma instância nomeada especificada por você).
ms.openlocfilehash: 5200562ce8db04b741bfba7f62fbe42a2c8f47df
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49803681"
---
# <a name="add-archiving-server-sql-server-store"></a>Adicionar Repositório do SQL Server para Servidor de Arquivamento

O Servidor de Arquivamento requer uma edição de 64 bits suportada do software de banco de dados do SQL Server para armazenar os dados de arquivo morto. Você pode selecionar um banco de dados do SQL Server definido anteriormente a ser usado para arquivamento ou definir um novo banco de dados do SQL Server especificando um FQDN (nome de domínio totalmente qualificado) do servidor no qual o banco de dados do SQL Server irá residir e a instância do SQL Server que você deseja usar para o novo banco de dados do SQL Server (que pode ser a instância padrão ou uma instância nomeada especificada por você).

> [!NOTE]
> Se a conta usada para publicar a topologia tiver os direitos de usuário e permissões apropriadas, será possível criar o banco de dados de arquivamento (LcsLog) ao publicar sua topologia. Também é possível criar o banco de dados posteriormente, como parte do procedimento de instalação, ou de outra forma.

> [!NOTE]
> Para instalar e implantar os bancos de dados no servidor baseado em SQL Server para arquivamento, você deve ser membro do grupo sysadmins do SQL Server para o servidor baseado em SQL Server onde você está instalando os arquivos de banco de dados. Se você não for membro do grupo sysadmins do SQL Server, deverá solicitar que seja adicionado ao grupo até que os arquivos de banco de dados sejam implantados. Se você não puder ser membro do grupo sysadmins, forneça ao administrador do banco de dados do SQL Server o script para configurar e implantar os bancos de dados. Para obter detalhes sobre os direitos e permissões de usuário necessários para realizar os procedimentos, consulte [Deployment Permissions for SQL Server](https://technet.microsoft.com/library/56ea0c02-bcf5-4d45-aa13-570531c29074.aspx) na documentação Implantação.


