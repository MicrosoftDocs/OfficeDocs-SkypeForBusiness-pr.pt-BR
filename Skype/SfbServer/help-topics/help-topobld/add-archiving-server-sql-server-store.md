---
title: Adicionar Repositório de Servidor SQL para Servidor de Arquivamento
ms.reviewer: ''
ms.author: v-mahoffman
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
ms.localizationpriority: medium
ms.assetid: 26e0a748-e31d-4c66-b225-b37e0a45408f
description: O Servidor de Arquivamento requer uma edição de 64 bits suportada do software SQL Server banco de dados para armazenar os dados de arquivo morto. Você pode selecionar um banco de dados de SQL Server definido anteriormente para ser usado para arquivamento ou definir um novo banco de dados SQL Server especificando um FQDN (nome de domínio totalmente qualificado) do servidor no qual o banco de dados SQL Server irá residir e a instância do SQL Server que você deseja usar para o novo datab SQL Server do SQL Server ase (que pode ser a instância padrão ou uma instância nomeada que você especificar).
ms.openlocfilehash: 2a892801dc0d971f64585e2e532dd22863b62c8c
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/04/2021
ms.locfileid: "60774181"
---
# <a name="add-archiving-server-sql-server-store"></a>Adicionar Repositório do SQL Server para Servidor de Arquivamento

O Servidor de Arquivamento requer uma edição de 64 bits suportada do software SQL Server banco de dados para armazenar os dados de arquivo morto. Você pode selecionar um banco de dados de SQL Server definido anteriormente para ser usado para arquivamento ou definir um novo banco de dados SQL Server especificando um FQDN (nome de domínio totalmente qualificado) do servidor no qual o banco de dados SQL Server irá residir e a instância do SQL Server que você deseja usar para o novo datab SQL Server do SQL Server ase (que pode ser a instância padrão ou uma instância nomeada que você especificar).

> [!NOTE]
> Se a conta usada para publicar a topologia tiver os direitos de usuário e permissões apropriadas, será possível criar o banco de dados de arquivamento (LcsLog) ao publicar sua topologia. Também é possível criar o banco de dados posteriormente, como parte do procedimento de instalação, ou de outra forma.

> [!NOTE]
> Para instalar e implantar os bancos de dados no servidor baseado em SQL Server para arquivamento, você deve ser membro do grupo SQL Server sysadmins para o servidor baseado em SQL Server onde você está instalando os arquivos de banco de dados. Se você não for membro do grupo SQL Server sysadmins, será necessário solicitar que sejam adicionados ao grupo até que os arquivos de banco de dados sejam implantados. Se você não puder ser membro do grupo sysadmins, deverá fornecer ao administrador do banco de dados SQL Server o script para configurar e implantar os bancos de dados. Para obter detalhes sobre os direitos e permissões de usuário necessários para realizar os procedimentos, consulte [Deployment Permissions for SQL Server](/previous-versions/office/lync-server-2013/lync-server-2013-deployment-permissions-for-sql-server) na documentação Implantação.