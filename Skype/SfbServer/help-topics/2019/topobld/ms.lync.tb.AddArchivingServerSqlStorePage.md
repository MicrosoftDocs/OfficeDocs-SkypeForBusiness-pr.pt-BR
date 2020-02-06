---
title: Adicionar Repositório de Servidor SQL para Servidor de Arquivamento
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.AddArchivingServerSqlStorePage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 26e0a748-e31d-4c66-b225-b37e0a45408f
ROBOTS: NOINDEX, NOFOLLOW
description: O servidor de arquivamento requer uma edição de 64 bits do software de banco de dados do SQL Server compatível para armazenar os dados de arquivo morto. Você pode selecionar um banco de dados do SQL Server definido anteriormente para ser usado para arquivar ou definir um novo banco de dados do SQL Server especificando um FQDN (nome de domínio totalmente qualificado) do servidor no qual o banco de dados do SQL Server residirá e a instância do SQL Server que você deseja usar para o novo banco de dados SQL Server (que pode ser a instância padrão ou uma instância nomeada que você especificar).
ms.openlocfilehash: 01153a976f404b1eac8176f55ffd7951d62975c9
ms.sourcegitcommit: b1229ed5dc25a04e56aa02aab8ad3d4209559d8f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41794850"
---
# <a name="add-archiving-server-sql-server-store"></a>Adicionar Repositório de Servidor SQL para Servidor de Arquivamento

O servidor de arquivamento requer uma edição de 64 bits do software de banco de dados do SQL Server compatível para armazenar os dados de arquivo morto. Você pode selecionar um banco de dados do SQL Server definido anteriormente para ser usado para arquivar ou definir um novo banco de dados do SQL Server especificando um FQDN (nome de domínio totalmente qualificado) do servidor no qual o banco de dados do SQL Server residirá e a instância do SQL Server que você deseja usar para o novo banco de dados SQL Server (que pode ser a instância padrão ou uma instância nomeada que você especificar).

> [!NOTE]
> Se a conta que é usada para publicar a topologia tiver os direitos de usuário e permissões apropriados, você poderá criar o banco de dados de arquivamento (LcsLog) quando publicar sua topologia. Você também pode criar o banco de dados posteriormente, como parte do procedimento de instalação ou de outra forma.

> [!NOTE]
> Para instalar e implantar os bancos de dados no servidor baseado em SQL Server para arquivamento, você deve ser membro do grupo Administradores do SQL Server para o servidor baseado em SQL Server no qual está instalando os arquivos do banco de dados. Se você não for membro do grupo Administradores do SQL Server, será necessário solicitar que seja adicionado ao grupo até que os arquivos de banco de dados sejam implantados. Se você não puder se tornar membro do grupo sysadmins, você deve fornecer o administrador do banco de dados do SQL Server com o script para configurar e implantar os bancos de dados. Para obter detalhes sobre os direitos e permissões de usuário que você precisa para executar os procedimentos, consulte [permissões de implantação do SQL Server](https://technet.microsoft.com/library/56ea0c02-bcf5-4d45-aa13-570531c29074.aspx) na documentação de implantação.


