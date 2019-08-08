---
title: Remover instâncias SQL Server e bancos de dados no Servidor Back-End
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Você remove os bancos de dados e instâncias do Microsoft SQL Server após remover os servidores em execução dependentes deles ou depois de reconfigurar os servidores para usar outro banco de dados. Você precisa executar o procedimento neste tópico quando desativar o SQL Server atual ou reconfigurar o servidor atual de modo que ele processe os bancos de dados obsoletos ou indisponíveis.
ms.openlocfilehash: 6c526499e3036c9a10b8dc92ccc519f21ae8bc96
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/07/2019
ms.locfileid: "36244198"
---
# <a name="remove-sql-server-instances-and-databases-on-the-back-end-server"></a>Remover instâncias SQL Server e bancos de dados no Servidor Back-End

Você remove os bancos de dados e instâncias do Microsoft SQL Server após remover os servidores em execução dependentes deles ou depois de reconfigurar os servidores para usar outro banco de dados. Você precisa executar o procedimento neste tópico quando desativar o SQL Server atual ou reconfigurar o servidor atual de modo que ele processe os bancos de dados obsoletos ou indisponíveis.
  
Para remover os bancos de dados ou instâncias do servidor de arquivamento ou Monitoring Server, primeiro você deve remover a função de servidor. Da mesma forma, para remover as instâncias ou os bancos de dados do pool de front-end, você deve primeiro remover ou reconfigurar a função de servidor dependente. Esses procedimentos não fazem distinção entre bancos de dados posicionados ou instâncias separadas para servidores. Os procedimentos não são afetados pela colocação de bancos de dados.
  
## <a name="in-this-section"></a>Nesta seção

- [Remover o banco de dados do Servidor SQL para um pool Front-End](remove-the-sql-server-database-for-a-front-end-pool.md)
    
- [Remover banco de dados do SQL Server de um servidor de Monitoramento](remove-the-sql-server-database-for-a-monitoring-server.md)
    
- [Remover o banco de dados do Servidor SQL de um servidor de Arquivamento](remove-the-sql-server-database-for-an-archiving-server.md)
    

