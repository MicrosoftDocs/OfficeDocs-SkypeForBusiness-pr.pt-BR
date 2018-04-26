---
title: Usar a OCT (Ferramenta de Personalização do Office) no Skype for Business Server 2015
ms.author: chucked
author: chuckedmonson
manager: serdars
ms.date: 10/20/2017
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 26647cb6-ba84-4ba7-8b6f-2cf86818e530
description: 'Resumo: como usar a Ferramenta de Personalização do Office com o cliente .'
ms.openlocfilehash: b0e8dd399af7a75a6f575d554cbe6c25c4e8ffd3
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/28/2018
---
# <a name="use-the-office-customization-tool-oct-in-skype-for-business-server-2015"></a>Usar a OCT (Ferramenta de Personalização do Office) no Skype for Business Server 2015
 
Resumo: como usar a Ferramenta de Personalização do Office com o cliente .
  
O Office Customization Tool (OCT) faz parte do programa de Instalação e é a ferramenta recomendada para várias personalizações. Ao usar o OCT, você personaliza o Office e salva suas personalizações em um arquivo msp de personalização de Instalação. Você coloca o arquivo na pasta Atualizações no ponto de instalação de rede. Ao instalar o Office, a Instalação procura por um arquivo de personalização da Instalação na pasta Atualizações e aplica as personalizações. A pasta Atualização pode ser usada apenas para implantar atualizações de software durante a instalação inicial do .
  
O OCT faz parte da instalação e está incluído em versões de licença de volume do produto. Você executa o OCT digitando  na linha de comando na raiz do ponto de instalação de rede que contém os arquivos de origem do . Por exemplo, use o seguinte:
  
 `\\server\share\Office15\setup.exe /admin`
  
Os administradores usam o OCT para criar um arquivo .msp de personalização da instalação. Como no OCT do , os administradores podem personalizar as seguintes áreas:
  
- **Instalação** Usado para especificar o local de instalação padrão no nome da organização padrão e cliente, fontes de instalação de rede adicionais, chave do produto, contrato de licença do usuário final, nível de exibição, versões anteriores do Office para remover, programas personalizados para executar durante a instalação, configurações de segurança e propriedades de Instalação.
    
- Usado para definir as configurações do usuário e personalizar como os recursos do Office são instalados. Os administradores podem usar o OCT para especificar os valores padrões iniciais das configurações do aplicativo do Office para usuários. Os usuários podem modificar a maioria das configurações após a instalação.
    
- **Conteúdo adicional** Usado para adicionar ou remover arquivos, adicionar ou remover entradas do Registro e configurar atalhos.
    
- **Outlook** Usado para personalizar o perfil padrão do Outlook do usuário, especificar as configurações do Exchange, adicionar contas, remover contas, exportar configurações e especificar grupos de Envio/Recebimento.
    
For information about the OCT, see [Use the OCT to customize Office 2013](https://technet.microsoft.com/library/cc179132.aspx). Note that this information also applies to Office 2016.
  

