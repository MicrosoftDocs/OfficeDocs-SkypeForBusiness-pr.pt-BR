---
title: Instalar Página de Opções de Banco de Dados
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1.keywords:
- NOCSH
ms.custom:
- ms.lync.tb.InstallDatabaseOptionPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 926c47a0-3957-4892-b61a-7a4b569552c3
description: 'Você configura opções avançadas para o posicionamento de arquivos de banco de dados e de log no SQL Server. As opções disponíveis são:'
ms.openlocfilehash: b24e79a837265930dd853590c9c3139c60a7abd4
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41819803"
---
# <a name="install-database-options-page"></a>Instalar Página de Opções de Banco de Dados

Você configura opções avançadas para o posicionamento de arquivos de banco de dados e de log no SQL Server. As opções disponíveis são:

> [!IMPORTANT]
> Selecione a opção que melhor se adapte às suas necessidades e políticas pertinentes ao posicionamento de dados e registros de arquivos em seus computadores SQL Server.

 **Determinar automaticamente o local do arquivo de banco de dados**: a opção padrão usa um algoritmo que determina o espaço disponível no SQL Server e distribui os arquivos de banco de dados e de log para obter ótimo desempenho.

 **Usar padrões de instância do SQL Server**: Selecione esta opção para colocar arquivos de banco de dados e arquivos de log com base nas configurações de instância no SQL Server. As opções são normalmente gerenciadas e configuradas pelo seu administrador de banco de dados.

 **Estes caminhos no SQL Server de destino**: Selecione esta opção para definir seus próprios caminhos para os arquivos de banco de dados e log do SQL Server digitando o caminho completo para a unidade e a pasta onde o banco de dados e os arquivos de log serão colocados.

> [!IMPORTANT]
> Os caminhos inseridos podem ser modificados com base em algoritmos de otimização de desempenho na instalação. Para obter detalhes, consulte [instalação de banco de dados usando o Shell de gerenciamento do Lync Server](https://technet.microsoft.com/library/c90a6449-4dd5-4b18-b21c-ea2c2a64dc3c.aspx).

 **OK**: clique no botão OK para confirmar as alterações.

 **Cancelar**: clique em Cancelar para descartar as alterações e retornar à tela do banco de dados de instalação.

 **Ajuda**: clique no botão ajuda para acessar esta página de ajuda.

## <a name="see-also"></a>Confira também

[Posicionamento de arquivos de log e dados do SQL Server](https://technet.microsoft.com/library/67aa525b-8aa3-474f-827e-8e1d4697f30f.aspx)
