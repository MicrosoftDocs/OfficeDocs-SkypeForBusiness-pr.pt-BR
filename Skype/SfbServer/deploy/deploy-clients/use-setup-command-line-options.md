---
title: Use as opções de linha de comando de instalação com Skype para clientes corporativos
ms.reviewer: ''
ms.author: chucked
author: chuckedmonson
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 99878c3c-ff31-48e2-8424-580d7b07a7bf
description: 'Resumo: Saiba sobre as operações de linha de comando Setup.exe na instalação do Office.'
ms.openlocfilehash: d3bf2b4d867fbbb43c346f2b9572de329ec66bdc
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/27/2019
ms.locfileid: "30880275"
---
# <a name="use-setup-command-line-options-with-skype-for-business-clients"></a>Use as opções de linha de comando de instalação com Skype para clientes corporativos
 
**Resumo:** Saiba mais sobre as operações de linha de comando Setup.exe na instalação do Office.
  
A linha de comando Setup.exe é usada em poucas operações na instalação do Office. Em vez de usar as opções de linha de comando da instalação, você geralmente usará a ferramenta de personalização do Office e o arquivo config. XML para personalização de instalação e o recurso de produto.
  
A linha de comando Setup.exe do Office reconhece as opções de linha de comando descritas na tabela a seguir.
  
**Opções de linha de comando Setup do Office**

|**Opção de linha de comando Setup**|**Descrição**|
|:-----|:-----|
|/admin  <br/> |Executa a Ferramenta de personalização do Office para criar um arquivo de personalização de Setup (arquivo .msp).  <br/> |
|/adminfile [caminho]  <br/> |Aplica o arquivo de personalização de Setup à instalação. Você pode especificar um caminho de arquivo de personalização específico (arquivo .msp) ou a pasta onde você armazena os arquivos de personalização.  <br/> |
|/config [caminho]  <br/> |Especifica o arquivo Config.xml que o Setup usa durante a instalação. Use a opção /config para especificar o arquivo config. XML que é personalizado para Skype para instalações de negócios, por exemplo:`/config \\server\share\Skype15\Skype.WW\Config.xml` <br/> |
|/modify Skype  <br/> |Usado com um arquivo Config.xml modificado para executar o Setup em modo de manutenção e fazer alterações à instalação existente do Office. Por exemplo, você pode usar o /Modify opção para adicionar ou remover Skype para recursos corporativos.  <br/> |
|/repair Skype  <br/> |Executa o Setup do computador do usuário para reparar Skype para negócios.  <br/> |
|/uninstall Skype  <br/> |Executa o Setup para remover Skype for Business do computador do usuário.  <br/> |
   


