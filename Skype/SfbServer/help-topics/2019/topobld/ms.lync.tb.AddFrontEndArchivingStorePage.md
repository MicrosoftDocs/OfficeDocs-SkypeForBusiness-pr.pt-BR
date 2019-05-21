---
title: Adicionar Repositório de Arquivamento Front End
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.AddFrontEndArchivingStorePage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: ce1723eb-7c93-424a-a622-9c888bf6d3bc
ROBOTS: NOINDEX, NOFOLLOW
description: O arquivamento requer uma edição de 64 bits com suporte do software de banco de dados do Microsoft SQL Server para armazenar os dados de arquivamento. Você pode selecionar um banco de dados do SQL Server definido anteriormente para ser usado para arquivamento ou definir um novo banco de dados do SQL Server especificando um FQDN (nome de domínio totalmente qualificado) do servidor no qual o banco de dados do SQL Server está para ficar, além da instância do SQL se rver que você deseja usar para o novo banco de dados SQL Server (que pode ser a instância padrão ou uma instância nomeada que você especificar).
ms.openlocfilehash: 5c55567b134af368296cc628e1e1297df1a8389a
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34283945"
---
# <a name="add-front-end-archiving-store"></a>Adicionar Repositório de Arquivamento Front End

O arquivamento requer uma edição de 64 bits com suporte do software de banco de dados do Microsoft SQL Server para armazenar os dados de arquivamento. Você pode selecionar um banco de dados do SQL Server definido anteriormente para ser usado para arquivamento ou definir um novo banco de dados do SQL Server especificando um FQDN (nome de domínio totalmente qualificado) do servidor no qual o banco de dados do SQL Server está para ficar, além da instância do SQL se rver que você deseja usar para o novo banco de dados SQL Server (que pode ser a instância padrão ou uma instância nomeada que você especificar).

> [!NOTE]
> Se a conta usada para publicar a topologia tiver os direitos de usuário e permissões apropriados, você poderá criar o banco de dados de monitoramento quando publicar sua topologia. Também é possível criar o banco de dados posteriormente, incluindo-o como parte do procedimento de instalação.

> [!NOTE]
> Para instalar e implantar os bancos de dados no servidor baseado em SQL Server para monitoramento, você deve ser um membro do grupo Administradores do SQL Server para o servidor baseado no SQL Server no qual está instalando os arquivos do banco de dados. Se você não for membro do grupo sysadmin do SQL Server, será necessário solicitar que você seja adicionado ao grupo até que os arquivos de banco de dados sejam implantados. Se você não puder se tornar membro do grupo sysadmins, você deve fornecer o administrador do banco de dados do SQL Server com o script para configurar e implantar os bancos de dados. Para obter detalhes sobre os direitos e permissões de usuário que você precisa para executar os procedimentos, consulte [permissões de implantação do SQL Server](https://technet.microsoft.com/library/56ea0c02-bcf5-4d45-aa13-570531c29074.aspx) na documentação de implantação.


