---
title: Usar opções de linha de comando Setup no Skype for Business Server 2015
ms.author: chucked
author: chuckedmonson
manager: serdars
ms.date: 10/20/2017
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 99878c3c-ff31-48e2-8424-580d7b07a7bf
description: 'Resumo: Saiba sobre as operações de linha de comando Setup.exe na instalação do Office.'
ms.openlocfilehash: 0fa4f31750697f0bd0dbe87bbde025cbc7f530bd
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/28/2018
---
# <a name="use-setup-command-line-options-in-skype-for-business-server-2015"></a>Usar opções de linha de comando Setup no Skype for Business Server 2015
 
**Resumo:** Saiba mais sobre as operações de linha de comando Setup.exe na instalação do Office.
  
A linha de comando Setup.exe é usada em poucas operações na instalação do Office. Em vez de usar as opções de linha de comando da instalação, você geralmente usará a ferramenta de personalização do Office e o arquivo config. XML para personalização de instalação e o recurso de produto.
  
A linha de comando Setup.exe do Office reconhece as opções de linha de comando descritas na tabela a seguir.
  
**Opções de linha de comando de instalação do Office**

|**Opção de linha de comando de instalação**|**Descrição**|
|:-----|:-----|
|/admin  <br/> |Executa a Ferramenta de personalização do Office para criar um arquivo de personalização de Setup (arquivo .msp).  <br/> |
|/adminfile [caminho]  <br/> |Aplica o arquivo de personalização de Setup à instalação. Você pode especificar um caminho de arquivo de personalização específico (arquivo .msp) ou a pasta onde você armazena os arquivos de personalização.  <br/> |
|/config [caminho]  <br/> |Especifica o arquivo Config.xml que o Setup usa durante a instalação. Use a opção /config para especificar o arquivo config. XML que é personalizado para Skype para instalações de negócios, por exemplo:`/config \\server\share\Skype15\Skype.WW\Config.xml` <br/> |
|/modify Skype  <br/> |Usado com um arquivo Config.xml modificado para executar o Setup em modo de manutenção e fazer alterações à instalação existente do Office. Por exemplo, você pode usar o /Modify opção para adicionar ou remover Skype para recursos corporativos.  <br/> |
|/repair Skype  <br/> |Executa o Setup do computador do usuário para reparar Skype para negócios.  <br/> |
|/uninstall Skype  <br/> |Executa o Setup para remover Skype for Business do computador do usuário.  <br/> |
   
Para obter detalhes sobre como usar as opções de linha de comando de instalação, consulte [https://go.microsoft.com/fwlink/p/?linkid=267515](https://go.microsoft.com/fwlink/p/?linkid=267515). 
  

