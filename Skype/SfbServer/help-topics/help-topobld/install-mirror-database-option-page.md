---
title: Instalar Página de Opção de Banco de Dados de Espelhamento
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1.keywords:
- ms.lync.tb.InstallMirrorDatabaseOptionPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 7500896a-14ea-4b11-aaee-be3d81314536
description: 'Defina as configurações do banco de dados espelho definindo o seguinte:'
ms.openlocfilehash: 4921182c8b6cb73c9cba5e7adeb791c482c46fd3
ms.sourcegitcommit: 19f534bfafbc74dbc2d381672b0650a3733cb982
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/03/2020
ms.locfileid: "41684634"
---
# <a name="install-mirror-database-option-page"></a>Instalar Página de Opção de Banco de Dados de Espelhamento
 
Defina as **configurações do banco de dados espelho** definindo o seguinte:
  
- Digite o **caminho para compartilhamento de arquivos** para definir o local dos arquivos do SQL Server de backup do banco de dados que está sendo espelhado.
    
    > [!NOTE]
    > A instância primária do SQL Server (instância nomeada ou padrão) deve ter permissões de gravação para o compartilhamento de arquivos que você definir aqui. A instância de espelhamento do SQL Server (instância nomeada ou padrão) deve ter permissões de leitura para o mesmo compartilhamento de arquivo. 
  
  **OK** Aceita e confirma as alterações na caixa de diálogo.
  
  **Cancelar** Descarta as alterações e fecha a caixa de diálogo.
  
  **Ajuda** Exibe essa tela de ajuda.
  
## <a name="see-also"></a>Confira também

[Implantar espelhamento de SQL para alta disponibilidade do servidor back-end no Skype for Business Server 2015](../../deploy/deploy-high-availability-and-disaster-recovery/sql-mirroring-for-high-availability.md)
