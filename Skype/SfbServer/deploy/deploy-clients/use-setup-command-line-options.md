---
title: Usar as opções de linha de comando de configuração com os clientes do Skype for Business
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 99878c3c-ff31-48e2-8424-580d7b07a7bf
description: 'Resumo: Saiba mais sobre as operações de linha de comando Setup. exe na instalação do Office.'
ms.openlocfilehash: 2eee24f9ae79ed2f73e23c68883f2552902fb672
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34306479"
---
# <a name="use-setup-command-line-options-with-skype-for-business-clients"></a>Usar as opções de linha de comando de configuração com os clientes do Skype for Business
 
**Resumo:** Saiba mais sobre as operações de linha de comando Setup. exe na instalação do Office.
  
A linha de comando Setup.exe é usada em poucas operações na instalação do Office. Em vez de usar as opções de linha de comando de configuração, você geralmente usará a ferramenta de personalização do Office e o arquivo config. xml para configuração do produto e personalização de recursos.
  
A linha de comando Setup.exe do Office reconhece as opções de linha de comando descritas na tabela a seguir.
  
**Opções de linha de comando Setup do Office**

|**Opção de linha de comando Setup**|**Descrição**|
|:-----|:-----|
|/admin  <br/> |Executa a Ferramenta de personalização do Office para criar um arquivo de personalização de Setup (arquivo .msp).  <br/> |
|/adminfile [caminho]  <br/> |Aplica o arquivo de personalização de Setup à instalação. Você pode especificar um caminho de arquivo de personalização específico (arquivo .msp) ou a pasta onde você armazena os arquivos de personalização.  <br/> |
|/config [caminho]  <br/> |Especifica o arquivo Config.xml que o Setup usa durante a instalação. Use a opção/config para especificar o arquivo config. xml personalizado para instalações do Skype for Business, por exemplo:`/config \\server\share\Skype15\Skype.WW\Config.xml` <br/> |
|/modify Skype  <br/> |Usado com um arquivo Config.xml modificado para executar o Setup em modo de manutenção e fazer alterações à instalação existente do Office. Por exemplo, você pode usar a opção/Modify para adicionar ou remover recursos do Skype for Business.  <br/> |
|/repair Skype  <br/> |Executa a instalação a partir do computador do usuário para reparar o Skype for Business.  <br/> |
|/uninstall Skype  <br/> |Executa a instalação para remover o Skype for Business do computador do usuário.  <br/> |
   


