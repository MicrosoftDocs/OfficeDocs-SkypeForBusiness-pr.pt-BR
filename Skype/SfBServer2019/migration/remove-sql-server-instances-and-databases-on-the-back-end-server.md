---
title: Remover instâncias SQL Server e bancos de dados no Servidor Back-End
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: Você remove os bancos de dados e instâncias do Microsoft SQL Server após remover os servidores em execução dependentes deles ou depois de reconfigurar os servidores para usar outro banco de dados. Você precisa executar o procedimento neste tópico quando desativar o SQL Server atual ou reconfigurar o servidor atual de modo que ele processe os bancos de dados obsoletos ou indisponíveis.
ms.openlocfilehash: 01552fcd494514802fffb35de7db7643f8cc26fd
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41812979"
---
# <a name="remove-sql-server-instances-and-databases-on-the-back-end-server"></a>Remover instâncias SQL Server e bancos de dados no Servidor Back-End

Você remove os bancos de dados e instâncias do Microsoft SQL Server após remover os servidores em execução dependentes deles ou depois de reconfigurar os servidores para usar outro banco de dados. Você precisa executar o procedimento neste tópico quando desativar o SQL Server atual ou reconfigurar o servidor atual de modo que ele processe os bancos de dados obsoletos ou indisponíveis.
  
Para remover os bancos de dados ou instâncias do servidor de arquivamento ou Monitoring Server, primeiro você deve remover a função de servidor. Da mesma forma, para remover as instâncias ou os bancos de dados do pool de front-end, você deve primeiro remover ou reconfigurar a função de servidor dependente. Esses procedimentos não fazem distinção entre bancos de dados posicionados ou instâncias separadas para servidores. Os procedimentos não são afetados pela colocação de bancos de dados.
  
## <a name="in-this-section"></a>Nesta seção

- [Remover o banco de dados do Servidor SQL para um pool Front-End](remove-the-sql-server-database-for-a-front-end-pool.md)
    
- [Remover banco de dados do SQL Server de um servidor de Monitoramento](remove-the-sql-server-database-for-a-monitoring-server.md)
    
- [Remover o banco de dados do Servidor SQL de um servidor de Arquivamento](remove-the-sql-server-database-for-an-archiving-server.md)
    

