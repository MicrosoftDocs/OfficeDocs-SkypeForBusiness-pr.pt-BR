---
title: Instalar Página de Opções de Banco de Dados
ms.reviewer: ''
ms.author: v-cichur
author: cichur
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
description: 'Você configura opções avançadas para o posicionamento de arquivos de banco de dados e de log no SQL Server. As opções disponíveis são:'
ms.openlocfilehash: f9c2553fb0a4fa8f538a70a2ce496eaf054a0dc4
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49806911"
---
# <a name="install-database-options-page"></a>Instalar Página de Opções de Banco de Dados

Você configura opções avançadas para o posicionamento de arquivos de banco de dados e de log no SQL Server. As opções disponíveis são:

> [!IMPORTANT]
> Selecione a opção que melhor se ajuste aos seus requisitos e políticas referentes ao posicionamento de arquivos de dados e de log nos computadores do SQL Server.

 **Determinar automaticamente o** local do arquivo de banco de dados: a opção padrão usa um algoritmo que determina o espaço disponível no SQL Server e distribui o banco de dados e os arquivos de log para obter o desempenho ideal.

 **Usar padrões de instância do SQL Server:** selecione essa opção para colocar arquivos de banco de dados e de log com base nas configurações da instância no SQL Server. As opções são normalmente gerenciadas e configuradas por seu Administrador de Banco de Dados.

 **Escolha este** caminho no SQL Server de destino: selecione essa opção para definir seus próprios caminhos para arquivos de log e de banco de dados do SQL Server digitando o caminho completo para a unidade e a pasta onde os arquivos de banco de dados e de log serão colocados.

> [!IMPORTANT]
> Os caminhos inseridos podem ser modificados com base nos algoritmos de otimização de desempenho na instalação. Para obter detalhes, consulte [Database Installation Using Lync Server Management Shell](https://technet.microsoft.com/library/c90a6449-4dd5-4b18-b21c-ea2c2a64dc3c.aspx).

 **OK**: clique no botão OK para confirmar suas alterações.

 **Cancelar**: clique em Cancelar para descartar quaisquer alterações e retornar à tela Instalar Banco de Dados.

 **Ajuda**: clique no botão Ajuda para acessar esta página de Ajuda.

## <a name="see-also"></a>Confira também

[Localização de arquivos de log e dados do SQL Server](https://technet.microsoft.com/library/67aa525b-8aa3-474f-827e-8e1d4697f30f.aspx)
