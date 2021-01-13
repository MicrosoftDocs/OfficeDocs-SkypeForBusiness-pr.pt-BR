---
title: Usar opções de linha de comando de Instalação com clientes do Skype for Business
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 99878c3c-ff31-48e2-8424-580d7b07a7bf
description: 'Resumo: saiba mais sobre Setup.exe de linha de comando na configuração do Office.'
ms.openlocfilehash: 042ba2bdea6228f7c8a726c0bdb2ca5c3233d5f4
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49837201"
---
# <a name="use-setup-command-line-options-with-skype-for-business-clients"></a>Usar opções de linha de comando de Instalação com clientes do Skype for Business
 
**Resumo:** Saiba mais sobre Setup.exe de linha de comando na configuração do Office.
  
A Setup.exe de comando é usada para poucas operações na configuração do Office. Em vez de usar as opções de linha de comando da Instalação, você normalmente usará a Ferramenta de Personalização do Office e o arquivo Config.xml para instalação do produto e personalização de recursos.
  
A linha Setup.exe comando do Office reconhece as opções de linha de comando descritas na tabela a seguir.
  
**Opções de configuração Command-Line Office**

|**Opção de Command-Line configuração**|**Descrição**|
|:-----|:-----|
|/admin  <br/> |Executa a Ferramenta de Personalização do Office para criar um arquivo de personalização da Instalação (arquivo .msp).  <br/> |
|/adminfile [path]  <br/> |Aplica o arquivo de personalização da Instalação específico para a instalação. É possível especificar um caminho de um arquivo de personalização específico (arquivo .msp) ou para a pasta na qual você armazena os arquivos de personalização.  <br/> |
|/config [path]  <br/> |Especifica o arquivo Config.xml que a Instalação usa durante a instalação. Use a opção /config para especificar o arquivo Config.xml personalizado para instalações do Skype for Business, por exemplo:  `/config \\server\share\Skype15\Skype.WW\Config.xml` <br/> |
|/modify Skype  <br/> |Usado com um arquivo Config.xml modificado para executar a instalação no modo de manutenção e fazer alterações em uma instalação existente do Office. Por exemplo, você pode usar a opção /modify para adicionar ou remover recursos do Skype for Business.  <br/> |
|/repair Skype  <br/> |Executa a Instalação do computador do usuário para reparar o Skype for Business.  <br/> |
|/uninstall Skype  <br/> |Executa a Instalação para remover o Skype for Business do computador do usuário.  <br/> |
   


