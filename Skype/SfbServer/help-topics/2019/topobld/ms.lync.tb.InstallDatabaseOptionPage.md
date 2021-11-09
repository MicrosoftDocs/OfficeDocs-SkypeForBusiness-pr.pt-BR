---
title: Instalar Página de Opções de Banco de Dados
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.InstallDatabaseOptionPage
ms.prod: skype-for-business-itpro
ms.localizationpriority: medium
ms.assetid: 926c47a0-3957-4892-b61a-7a4b569552c3
ROBOTS: NOINDEX, NOFOLLOW
description: 'Você configura opções avançadas para o posicionamento de arquivos de banco de dados e de log em seu SQL Server. As opções disponíveis são:'
ms.openlocfilehash: 4ef2f2aa48b016a8472f53ccef46ef81a5afd6fb
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/08/2021
ms.locfileid: "60830425"
---
# <a name="install-database-options-page"></a>Instalar Página de Opções de Banco de Dados

Você configura opções avançadas para o posicionamento de arquivos de banco de dados e de log em seu SQL Server. As opções disponíveis são:

> [!IMPORTANT]
> Selecione a opção que melhor se ajuste aos seus requisitos e políticas referentes ao posicionamento de arquivos de log e dados em seus SQL Server computadores.

 **Determinar automaticamente o** local do arquivo de banco de dados : A opção padrão usa um algoritmo que determina o espaço disponível no SQL Server e distribui o banco de dados e os arquivos de log para obter o desempenho ideal.

 **Use SQL Server de instância:** selecione essa opção para colocar arquivos de banco de dados e arquivos de log com base nas configurações de instância em SQL Server. As opções são normalmente gerenciadas e configuradas por seu Administrador de Banco de Dados.

 Us **these path on target SQL Server**: Select this option to define your own paths for SQL Server database and log files by typing the full path to the drive and folder where the database and log files will be placed.

> [!IMPORTANT]
> Os caminhos inseridos podem ser modificados com base nos algoritmos de otimização de desempenho na instalação. Para obter detalhes, consulte [Database Installation Using Lync Server Management Shell](/previous-versions/office/lync-server-2013/lync-server-2013-database-installation-using-lync-server-management-shell).

 **OK**: clique no botão OK para confirmar suas alterações.

 **Cancelar**: clique em Cancelar para descartar quaisquer alterações e retornar à tela Instalar Banco de Dados.

 **Ajuda**: clique no botão Ajuda para acessar esta página de Ajuda.

## <a name="see-also"></a>Confira também

[Localização de arquivos de log e dados do SQL Server](/previous-versions/office/lync-server-2013/lync-server-2013-sql-server-data-and-log-file-placement)