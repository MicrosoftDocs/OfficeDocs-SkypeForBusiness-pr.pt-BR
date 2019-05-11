---
title: Instalar Página de Opções de Banco de Dados
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.InstallDatabaseOptionPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 926c47a0-3957-4892-b61a-7a4b569552c3
ROBOTS: NOINDEX, NOFOLLOW
description: 'Você configurar opções avançadas para o posicionamento de arquivos de log e de banco de dados no SQL Server. As opções disponíveis são:'
ms.openlocfilehash: e503a9daf167da576e552f5f77160a7289639bee
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "33919742"
---
# <a name="install-database-options-page"></a>Instalar Página de Opções de Banco de Dados

Você configurar opções avançadas para o posicionamento de arquivos de log e de banco de dados no SQL Server. As opções disponíveis são:

> [!IMPORTANT]
> Selecione a opção que melhor atenda aos seus requisitos e políticas referentes ao posicionamento de arquivos de dados e log em seus computadores SQL Server.

 **Determinar o local do arquivo de banco de dados automaticamente**: A opção padrão usa um algoritmo que determina o espaço disponível no SQL Server e distribui os arquivos de banco de dados e log para um desempenho ideal.

 **Use o SQL Server instância padrões**: Selecione essa opção para colocar o arquivo de banco de dados e log de arquivos com base nas configurações da instância no SQL Server. Normalmente, as opções são gerenciadas e configuradas pelo administrador de banco de dados.

 **Com esses caminho no SQL Server alvo**: Selecione essa opção para definir suas próprias caminhos para os arquivos de log e de banco de dados do SQL Server, digitando o caminho completo para a unidade e a pasta onde os arquivos de log e de banco de dados serão colocados.

> [!IMPORTANT]
> Os caminhos que você insira podem ser modificados com base em algoritmos de otimização de desempenho na sua instalação. Para obter detalhes, consulte [Banco de dados de instalação usando o Lync Server Management Shell](https://technet.microsoft.com/library/c90a6449-4dd5-4b18-b21c-ea2c2a64dc3c.aspx).

 **Okey**: clique no botão Okey para confirmar suas alterações.

 **Cancelar**: clique em Cancelar para descartar quaisquer alterações e retornar à tela Instalar banco de dados.

 **Ajuda**: clique no botão Ajuda para acessar esta página de Ajuda.

## <a name="see-also"></a>Confira também

[Localização do arquivo de Log e de dados do SQL Server](https://technet.microsoft.com/library/67aa525b-8aa3-474f-827e-8e1d4697f30f.aspx)
