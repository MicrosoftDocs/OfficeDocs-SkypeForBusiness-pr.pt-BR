---
title: Instalar e Criar Bancos de Dados
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.InstallDatabaseCreateDatabasePage
ms.prod: skype-for-business-itpro
ms.localizationpriority: medium
ms.assetid: 515754ad-1344-42dc-8219-ee973de2e4c4
description: Selecione os bancos de dados que você deseja criar para sua implantação. Por padrão, o banco de dados será criado no SQL Server definido no site definido e implantará e configurará automaticamente os arquivos de banco de dados com base no SQL Server em que você está colocando os bancos de dados.
ms.openlocfilehash: 67d30a8f9997435175a0b90067d5f61de51be202
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/04/2021
ms.locfileid: "60770469"
---
# <a name="install-and-create-databases"></a>Instalar e Criar Bancos de Dados

Selecione os bancos de dados que você deseja criar para sua implantação. Por padrão, o banco de dados será criado no SQL Server definido no site definido e implantará e configurará automaticamente os arquivos de banco de dados com base no SQL Server em que você está colocando os bancos de dados.

 **Selecione os bancos de dados que deseja criar**: marque a caixa de seleção de qualquer banco de dados que você pretenda implantar e configurar. Marque a caixa de seleção ou qualquer um ou todos os bancos de dados que você implantará.

> [!CAUTION]
> A SQL Server já deve ter sido configurada para a instância (se alguma) e as portas de firewall devem ser abertas para acomodar a instância em que você está implantando os bancos de dados. Para obter detalhes, consulte [Configure SQL Server for Lync Server 2013 Preview](/previous-versions/office/lync-server-2013/lync-server-2013-configure-sql-server-for-lync-server)

 **Avançado**: clique na SQL Server e clique no botão **Avançado** para escolher opções para os locais de arquivo de banco de dados em sua SQL Server. Para obter detalhes sobre o posicionamento avançado de arquivo de banco de dados, consulte [Database Installation Using Lync Server Management Shell](/previous-versions/office/lync-server-2013/lync-server-2013-database-installation-using-lync-server-management-shell)

 **Voltar**: clicar nesse botão faz com que você volte para a tela anterior (talvez não esteja sempre disponível, com base na forma que você chegou até essa caixa de diálogo).

 **Avançar**: clicar nesse botão confirma sua seleção na caixa de diálogo atual e o leva até a próxima caixa de diálogo para configurar informações adicionais

 **Cancelar**: clicar nesse botão encerrará a configuração e descartará suas alterações. Algumas telas de configuração, mas não todas, perguntarão se você deseja encerrar e descartar suas alterações. Selecionar **Sim** fechará a configuração atual e fechará a configuração atual e o retornará ao Construtor de Topologias. Selecionar **Não** o levará de volta até a caixa de diálogo de configuração atual e permitirá que você continue a configuração.

 **Ajudar**: clicar no botão **Ajuda** exibe essas informações de ajuda associadas à caixa de diálogo de configuração atual.