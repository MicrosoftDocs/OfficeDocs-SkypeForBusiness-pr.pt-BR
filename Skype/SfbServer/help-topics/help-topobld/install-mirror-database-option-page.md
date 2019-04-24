---
title: Instalar Página de Opção de Banco de Dados de Espelhamento
ms.reviewer: ''
ms.author: heidip
author: microsoftheidi
manager: serdars
ms.date: 11/17/2018
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.InstallMirrorDatabaseOptionPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 7500896a-14ea-4b11-aaee-be3d81314536
description: 'Você pode configurar definições de banco de dados de espelho definindo o seguinte:'
ms.openlocfilehash: 2a468333fff6cde69ce96eaf3d9170500bfb6648
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/23/2019
ms.locfileid: "32200226"
---
# <a name="install-mirror-database-option-page"></a>Instalar Página de Opção de Banco de Dados de Espelhamento
 
Você pode configurar **Definições de banco de dados de espelho** definindo o seguinte:
  
- Digite o **caminho do arquivo compartilhar** para definir o local dos arquivos de backup do SQL Server para o banco de dados sendo espelhado.
    
    > [!NOTE]
    > Instância do SQL Server principal (instância nomeada ou instância padrão) deve ter permissões de gravação para o compartilhamento de arquivos definidas aqui. O espelho (instância nomeada ou instância padrão) a instância do SQL Server deve ter permissões de leitura para o mesmo compartilhamento de arquivo. 
  
  **OK** Aceita e confirma as alterações na caixa de diálogo.
  
  **Cancelar** Descarta as alterações e fecha a caixa de diálogo.
  
  **Ajuda** Exibe essa tela de ajuda.
  
## <a name="see-also"></a>Confira também

[Implantar espelhamento de SQL para alta disponibilidade do servidor back-end no Skype for Business Server 2015](../../deploy/deploy-high-availability-and-disaster-recovery/sql-mirroring-for-high-availability.md)
