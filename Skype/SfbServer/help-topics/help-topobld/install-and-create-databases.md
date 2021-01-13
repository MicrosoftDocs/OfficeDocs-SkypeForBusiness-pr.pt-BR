---
title: Instalar e Criar Bancos de Dados
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
- ms.lync.tb.InstallDatabaseCreateDatabasePage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 515754ad-1344-42dc-8219-ee973de2e4c4
description: Selecione os bancos de dados que você deseja criar para sua implantação. Por padrão, o banco de dados será criado no SQL Server definido no site definido e implantará e configurará automaticamente os arquivos de banco de dados com base no SQL Server em que você está colocando os bancos de dados.
ms.openlocfilehash: 36912e468b0618925b3fbeb20db829d8d19249fa
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49806931"
---
# <a name="install-and-create-databases"></a>Instalar e Criar Bancos de Dados

Selecione os bancos de dados que você deseja criar para sua implantação. Por padrão, o banco de dados será criado no SQL Server definido no site definido e implantará e configurará automaticamente os arquivos de banco de dados com base no SQL Server em que você está colocando os bancos de dados.

 **Selecione os bancos de dados que deseja criar**: marque a caixa de seleção de qualquer banco de dados que você pretenda implantar e configurar. Marque a caixa de seleção ou qualquer um ou todos os bancos de dados que você implantará.

> [!CAUTION]
> O SQL Server já deve ter sido configurado para a instância (se for o caso) e as portas de firewall devem ser abertas para acomodar a instância em que você está implantando os bancos de dados. Para obter detalhes, consulte [Configure SQL Server for Lync Server 2013 Preview](https://technet.microsoft.com/library/375e5cc4-e436-46dc-9b02-5063f35cdcc1.aspx)

 **Avançado:** clique no SQL Server e clique no **botão** Avançado para escolher opções para os locais de arquivo de banco de dados no SQL Server. Para obter detalhes sobre o posicionamento avançado de arquivo de banco de dados, consulte [Database Installation Using Lync Server Management Shell](https://technet.microsoft.com/library/c90a6449-4dd5-4b18-b21c-ea2c2a64dc3c.aspx)

 **Voltar**: clicar nesse botão faz com que você volte para a tela anterior (talvez não esteja sempre disponível, com base na forma que você chegou até essa caixa de diálogo).

 **Avançar**: clicar nesse botão confirma sua seleção na caixa de diálogo atual e o leva até a próxima caixa de diálogo para configurar informações adicionais

 **Cancelar**: clicar nesse botão encerrará a configuração e descartará suas alterações. Algumas telas de configuração, mas não todas, perguntarão se você deseja encerrar e descartar suas alterações. Selecionar **Sim fechará** a configuração atual, fechará a configuração atual e o retornará ao Construtor de Topologias. Selecionar **Não** o levará de volta até a caixa de diálogo de configuração atual e permitirá que você continue a configuração.

 **Ajudar**: clicar no botão **Ajuda** exibe essas informações de ajuda associadas à caixa de diálogo de configuração atual.


