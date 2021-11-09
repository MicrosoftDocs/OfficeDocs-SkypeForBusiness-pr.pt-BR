---
title: Usar opções de linha de comando de instalação com Skype for Business clientes
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: 99878c3c-ff31-48e2-8424-580d7b07a7bf
description: 'Resumo: saiba mais sobre Setup.exe de linha de comando na Office configuração.'
ms.openlocfilehash: 6a64ac821019f49f8cbb4988ad0e42da0363245b
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/08/2021
ms.locfileid: "60850475"
---
# <a name="use-setup-command-line-options-with-skype-for-business-clients"></a>Usar opções de linha de comando de instalação com Skype for Business clientes
 
**Resumo:** Saiba mais sobre Setup.exe de linha de comando na Office configuração.
  
A Setup.exe de comando é usada para muito poucas operações na Office configuração. Em vez de usar as opções de linha de comando de Instalação, normalmente você usará a Ferramenta de Personalização Office e o arquivo Config.xml para configuração do produto e personalização de recursos.
  
A Office Setup.exe de comando reconhece as opções de linha de comando descritas na tabela a seguir.
  
**Office Opções Command-Line configuração**

|**Opção Command-Line instalação**|**Descrição**|
|:-----|:-----|
|/admin  <br/> |Executa a Ferramenta de Personalização do Office para criar um arquivo de personalização da Instalação (arquivo .msp).  <br/> |
|/adminfile [path]  <br/> |Aplica o arquivo de personalização da Instalação específico para a instalação. É possível especificar um caminho de um arquivo de personalização específico (arquivo .msp) ou para a pasta na qual você armazena os arquivos de personalização.  <br/> |
|/config [path]  <br/> |Especifica o arquivo Config.xml que a Instalação usa durante a instalação. Use a opção /config para especificar o arquivo Config.xml personalizado para instalações Skype for Business, por exemplo:`/config \\server\share\Skype15\Skype.WW\Config.xml` <br/> |
|/modify Skype  <br/> |Usado com um arquivo Config.xml modificado para executar a instalação no modo de manutenção e fazer alterações em uma instalação existente do Office. Por exemplo, você pode usar a opção /modify para adicionar ou remover Skype for Business recursos.  <br/> |
|/repair Skype  <br/> |Executa a Instalação do computador do usuário para reparar Skype for Business.  <br/> |
|/uninstall Skype  <br/> |Executa a Instalação para remover Skype for Business do computador do usuário.  <br/> |
   


