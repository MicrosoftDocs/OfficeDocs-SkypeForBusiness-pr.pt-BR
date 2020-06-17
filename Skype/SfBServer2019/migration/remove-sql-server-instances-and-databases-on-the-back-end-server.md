---
title: Remover instâncias SQL Server e bancos de dados no Servidor Back-End
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: Você remove os bancos de dados e instâncias do Microsoft SQL Server depois de remover os servidores que estão em execução dependem deles ou após reconfigurar os servidores para usar outro banco de dados. Você precisa executar o procedimento neste tópico quando você desativa o SQL Server atual ou reconfigura o servidor atual de forma que ele processe os bancos de dados obsoletos ou indisponíveis.
ms.openlocfilehash: 6e108e4dfef86b482b839bd440f54702ab42107d
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/16/2020
ms.locfileid: "44752153"
---
# <a name="remove-sql-server-instances-and-databases-on-the-back-end-server"></a>Remover instâncias SQL Server e bancos de dados no Servidor Back-End

Você remove os bancos de dados e instâncias do Microsoft SQL Server depois de remover os servidores que estão em execução dependem deles ou após reconfigurar os servidores para usar outro banco de dados. Você precisa executar o procedimento neste tópico quando você desativa o SQL Server atual ou reconfigura o servidor atual de forma que ele processe os bancos de dados obsoletos ou indisponíveis.
  
Para remover os bancos de dados ou instâncias do servidor de arquivamento ou do Monitoring Server, primeiro você deve remover a função de servidor. Da mesma forma, para remover as instâncias ou os bancos de dados do pool de front-ends, primeiro você deve remover ou reconfigurar a função de servidor dependente. Esses procedimentos não fazem distinção entre bancos de dados colocados ou instâncias separadas. Os procedimentos não são afetados pela colocação do banco de dados.
  
## <a name="in-this-section"></a>Nesta seção

- [Remover o banco de dados do Servidor SQL para um pool Front-End](remove-the-sql-server-database-for-a-front-end-pool.md)
    
- [Remover banco de dados do SQL Server de um servidor de Monitoramento](remove-the-sql-server-database-for-a-monitoring-server.md)
    
- [Remover o banco de dados do Servidor SQL de um servidor de Arquivamento](remove-the-sql-server-database-for-an-archiving-server.md)
    

