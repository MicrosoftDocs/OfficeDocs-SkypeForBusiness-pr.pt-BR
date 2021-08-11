---
title: Adicionar Repositório de Arquivamento Front End
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
- ms.lync.tb.AddFrontEndArchivingStorePage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: ce1723eb-7c93-424a-a622-9c888bf6d3bc
description: O arquivamento requer uma edição de 64 bits suportada do software de banco de dados Microsoft SQL Server para armazenar os dados de arquivamento. Você pode selecionar um banco de dados de SQL Server definido anteriormente para ser usado para arquivamento ou definir um novo banco de dados SQL Server especificando um FQDN (nome de domínio totalmente qualificado) do servidor no qual o banco de dados SQL Server deve residir, além da instância do SQL Server que você deseja usar para o novo banco de dados SQL Server (que pode ser a instância padrão ou uma instância nomeada que você especificar).
ms.openlocfilehash: 46f1d06994ce88800432ca9e653555b05c5756710127ad90d70e624e35bdd8dc
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/05/2021
ms.locfileid: "54321733"
---
# <a name="add-front-end-archiving-store"></a>Adicionar Repositório de Arquivamento Front-end

O arquivamento requer uma edição de 64 bits suportada do software de banco de dados Microsoft SQL Server para armazenar os dados de arquivamento. Você pode selecionar um banco de dados de SQL Server definido anteriormente para ser usado para arquivamento ou definir um novo banco de dados SQL Server especificando um FQDN (nome de domínio totalmente qualificado) do servidor no qual o banco de dados SQL Server deve residir, além da instância do SQL Server que você deseja usar para o novo banco de dados SQL Server (que pode ser a instância padrão ou uma instância nomeada que você especificar).

> [!NOTE]
> Se a conta usada para publicar a topologia tiver os direitos de usuário e permissões apropriadas, será possível criar o banco de dados de monitoramento ao publicar sua topologia. Também é possível criar o banco de dados posteriormente, incluído como parte do procedimento de instalação.

> [!NOTE]
> Para instalar e implantar os bancos de dados no servidor baseado em SQL Server para monitoramento, você deve ser membro do grupo SQL Server sysadmins para o servidor baseado em SQL Server onde você está instalando os arquivos de banco de dados. Se você não for membro do grupo SQL Server sysadmin, deverá solicitar que você seja adicionado ao grupo até que os arquivos de banco de dados sejam implantados. Se você não puder ser membro do grupo sysadmins, deverá fornecer ao administrador do banco de dados SQL Server o script para configurar e implantar os bancos de dados. Para obter detalhes sobre os direitos e permissões de usuário necessários para realizar os procedimentos, consulte [Deployment Permissions for SQL Server](/previous-versions/office/lync-server-2013/lync-server-2013-deployment-permissions-for-sql-server) na documentação Implantação.