---
title: Adicionar Repositório de Arquivamento Front End
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.AddFrontEndArchivingStorePage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: ce1723eb-7c93-424a-a622-9c888bf6d3bc
ROBOTS: NOINDEX, NOFOLLOW
description: O arquivamento requer uma edição de 64 bits suportada do software de banco de dados do Microsoft SQL Server para armazenar os dados de arquivamento. Você pode selecionar um banco de dados sql Server definido anteriormente a ser usado para arquivamento ou definir um novo banco de dados do SQL Server especificando um FQDN (nome de domínio totalmente qualificado) do servidor no qual o banco de dados do SQL Server deve residir, além da instância do SQL Server que você deseja usar para o novo banco de dados do SQL Server (que pode ser a instância padrão ou uma instância nomeada especificada por você).
ms.openlocfilehash: a0a9528b141730da91d233774a6c676956c9b19b
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49833521"
---
# <a name="add-front-end-archiving-store"></a>Adicionar Repositório de Arquivamento Front-end

O arquivamento requer uma edição de 64 bits suportada do software de banco de dados do Microsoft SQL Server para armazenar os dados de arquivamento. Você pode selecionar um banco de dados sql Server definido anteriormente a ser usado para arquivamento ou definir um novo banco de dados do SQL Server especificando um FQDN (nome de domínio totalmente qualificado) do servidor no qual o banco de dados do SQL Server deve residir, além da instância do SQL Server que você deseja usar para o novo banco de dados do SQL Server (que pode ser a instância padrão ou uma instância nomeada especificada por você).

> [!NOTE]
> Se a conta usada para publicar a topologia tiver os direitos de usuário e permissões apropriadas, será possível criar o banco de dados de monitoramento ao publicar sua topologia. Também é possível criar o banco de dados posteriormente, incluído como parte do procedimento de instalação.

> [!NOTE]
> Para instalar e implantar os bancos de dados no servidor baseado em SQL Server para monitoramento, você deve ser membro do grupo sysadmins do SQL Server para o servidor baseado em SQL Server em que você está instalando os arquivos de banco de dados. Se você não for membro do grupo sysadmin do SQL Server, deverá solicitar que seja adicionado ao grupo até que os arquivos de banco de dados sejam implantados. Se você não puder ser membro do grupo sysadmins, forneça ao administrador do banco de dados do SQL Server o script para configurar e implantar os bancos de dados. Para obter detalhes sobre os direitos e permissões de usuário necessários para realizar os procedimentos, consulte [Deployment Permissions for SQL Server](https://technet.microsoft.com/library/56ea0c02-bcf5-4d45-aa13-570531c29074.aspx) na documentação Implantação.


