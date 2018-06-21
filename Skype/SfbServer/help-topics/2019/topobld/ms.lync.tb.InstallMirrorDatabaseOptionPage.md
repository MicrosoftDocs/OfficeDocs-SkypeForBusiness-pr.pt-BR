---
title: Instalar página de opção de banco de dados de espelho
ms.author: heidip
author: microsoftheidi
manager: serdars
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.InstallMirrorDatabaseOptionPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 7500896a-14ea-4b11-aaee-be3d81314536
description: 'Você pode configurar definições de banco de dados de espelho definindo o seguinte:'
ms.openlocfilehash: 2cd793883baf5e5d567e9248e60f6601f8e1aa96
ms.sourcegitcommit: 08cf97296fb9ba6fbc4d68c3e380c8f37e86dd02
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/21/2018
ms.locfileid: "19989759"
---
# <a name="install-mirror-database-option-page"></a>Instalar página de opção de banco de dados de espelho
 
Você pode configurar **Definições de banco de dados de espelho** definindo o seguinte:
  
- Digite o **caminho do arquivo compartilhar** para definir o local dos arquivos de backup do SQL Server para o banco de dados sendo espelhado.
    
    > [!NOTE]
    > Instância do SQL Server principal (instância nomeada ou instância padrão) deve ter permissões de gravação para o compartilhamento de arquivos definidas aqui. O espelho (instância nomeada ou instância padrão) a instância do SQL Server deve ter permissões de leitura para o mesmo compartilhamento de arquivo. 
  
 **OK** Aceita e confirma as alterações na caixa de diálogo.
  
 **Cancelar** Descarta as alterações e fecha a caixa de diálogo.
  
 **Ajuda** Exibe essa tela de ajuda.
  
## <a name="see-also"></a>Consulte também

[Implantar o espelhamento do SQL para alta disponibilidade do servidor Back-End no Skype para Business Server](../../../deploy/deploy-high-availability-and-disaster-recovery/sql-mirroring-for-high-availability.md)