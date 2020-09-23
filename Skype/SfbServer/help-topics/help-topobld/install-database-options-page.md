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
- CSH
ms.custom:
- ms.lync.tb.InstallDatabaseOptionPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 926c47a0-3957-4892-b61a-7a4b569552c3
description: 'Você configura opções avançadas para o posicionamento de banco de dados e arquivos de log no SQL Server. As opções disponíveis são:'
ms.openlocfilehash: 4c8c456aa1fd0e9eee150e184b4d1f7934c26b65
ms.sourcegitcommit: c69ab11b701a4833179b8479bc3204dfd4412096
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/23/2020
ms.locfileid: "48215302"
---
# <a name="install-database-options-page"></a>Instalar Página de Opções de Banco de Dados

Você configura opções avançadas para o posicionamento de banco de dados e arquivos de log no SQL Server. As opções disponíveis são:

> [!IMPORTANT]
> Selecione a opção que melhor atende aos seus requisitos e políticas referentes aos dados e à colocação de arquivos de log em seus computadores do SQL Server.

 **Determinar automaticamente o local do arquivo de banco de dados**: a opção padrão usa um algoritmo que determina o espaço disponível no SQL Server e distribui os arquivos de banco de dados e de log para obter o melhor desempenho.

 **Usar padrões de instância do SQL Server**: Selecione essa opção para colocar arquivos de log e arquivo de banco de dados com base nas configurações de instância do SQL Server. As opções são normalmente gerenciadas e configuradas por seu Administrador de Banco de Dados.

 **Estes caminhos no SQL Server de destino**: Selecione essa opção para definir seus próprios caminhos para os arquivos de banco de dados e de log do SQL Server digitando o caminho completo para a unidade e a pasta onde os arquivos de banco de dados e de log serão colocados.

> [!IMPORTANT]
> Os caminhos inseridos podem ser modificados com base nos algoritmos de otimização de desempenho na instalação. Para obter detalhes, consulte [Database Installation Using Lync Server Management Shell](https://technet.microsoft.com/library/c90a6449-4dd5-4b18-b21c-ea2c2a64dc3c.aspx).

 **OK**: clique no botão OK para confirmar suas alterações.

 **Cancelar**: clique em Cancelar para descartar quaisquer alterações e retornar à tela Instalar Banco de Dados.

 **Ajuda**: clique no botão Ajuda para acessar esta página de Ajuda.

## <a name="see-also"></a>Confira também

[Localização de arquivos de log e dados do SQL Server](https://technet.microsoft.com/library/67aa525b-8aa3-474f-827e-8e1d4697f30f.aspx)
