---
title: Adicionar Repositório de Servidor SQL de Servidor de Monitoramento
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.AddMonitoringServerSqlStorePage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: d873a2ad-9d3a-4ef6-9f25-ccdd3716218c
ROBOTS: NOINDEX, NOFOLLOW
description: O Monitoring Server exige uma edição de 64 bits do software de banco de dados do SQL Server compatível para armazenar os dados de monitoramento. Você pode selecionar um banco de dados do SQL Server definido anteriormente para ser usado para monitoramento ou definir um novo banco de dados do SQL Server especificando um FQDN (nome de domínio totalmente qualificado) do servidor no qual o banco de dados do SQL Server residirá, além da instância do SQL Server que você deseja usar para o novo banco de dados SQL Server (que pode ser a instância padrão ou uma instância nomeada que você especificar).
ms.openlocfilehash: b51d4802d67175177ca48419f495cbbccf981f4f
ms.sourcegitcommit: b1229ed5dc25a04e56aa02aab8ad3d4209559d8f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41798458"
---
# <a name="add-monitoring-server-sql-server-store"></a>Adicionar Repositório de Servidor SQL de Servidor de Monitoramento

O Monitoring Server exige uma edição de 64 bits do software de banco de dados do SQL Server compatível para armazenar os dados de monitoramento. Você pode selecionar um banco de dados do SQL Server definido anteriormente para ser usado para monitoramento ou definir um novo banco de dados do SQL Server especificando um FQDN (nome de domínio totalmente qualificado) do servidor no qual o banco de dados do SQL Server residirá, além da instância do SQL Server que você deseja usar para o novo banco de dados SQL Server (que pode ser a instância padrão ou uma instância nomeada que você especificar).

Para obter detalhes sobre o suporte do SQL Server, consulte [suporte a cluster e software de banco de dados](https://technet.microsoft.com/library/e05d0032-bbea-4e61-987d-d07b1c045fd5.aspx) na documentação de suporte. Para obter detalhes sobre o banco de dados de monitoramento, incluindo a colocação do banco de dados de monitoramento, consulte [localização de servidor com suporte](https://technet.microsoft.com/library/3be990a1-5485-4b83-b73f-947ac97821f9.aspx) na documentação de suporte,[planejando o monitoramento](https://technet.microsoft.com/library/26cead5a-183c-42f1-a4b0-0e8d61c6159d.aspx) nos dados de documentação de planejamento e [dados do SQL Server e na localização de arquivos de log](https://technet.microsoft.com/library/67aa525b-8aa3-474f-827e-8e1d4697f30f.aspx) na documentação de implantação.

> [!NOTE]
> Se a conta usada para publicar a topologia tiver os direitos de usuário e permissões apropriados, você poderá criar o banco de dados de monitoramento quando publicar sua topologia. Você também pode criar o banco de dados posteriormente, incluindo como parte do procedimento de instalação. > instalar e implantar os bancos de dados no servidor baseado no SQL Server para monitoramento, você deve ser membro do grupo Administradores do SQL Server para o servidor baseado no SQL Server no qual está instalando os arquivos do banco de dados. Se você não for membro do grupo sysadmin do SQL Server, será necessário solicitar que seja adicionado ao grupo até que os arquivos de banco de dados sejam implantados. Se você não puder se tornar membro do grupo sysadmins, você deve fornecer o administrador do banco de dados do SQL Server com o script para configurar e implantar os bancos de dados. Para obter detalhes sobre os direitos e permissões de usuário que você precisa para realizar esses procedimentos, consulte [permissões de implantação do SQL Server](https://technet.microsoft.com/library/56ea0c02-bcf5-4d45-aa13-570531c29074.aspx) na documentação de implantação.


