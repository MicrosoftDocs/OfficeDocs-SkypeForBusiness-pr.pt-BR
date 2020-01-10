---
title: Usar a ferramenta de personalização do Office (OCT) no Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 26647cb6-ba84-4ba7-8b6f-2cf86818e530
description: 'Resumo: como usar a ferramenta de personalização do Office com o cliente Skype for Business.'
ms.openlocfilehash: b5c66fee4f6c879c8ded2897b64e63654dd950be
ms.sourcegitcommit: fe274303510d07a90b506bfa050c669accef0476
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/09/2020
ms.locfileid: "41001591"
---
# <a name="use-the-office-customization-tool-oct-in-skype-for-business-server"></a>Usar a ferramenta de personalização do Office (OCT) no Skype for Business Server
 
**Resumo:** Como usar a ferramenta de personalização do Office com o cliente Skype for Business.
  
O Office Customization Tool (OCT) faz parte do programa de Instalação e é a ferramenta recomendada para várias personalizações. Ao usar o OCT, você personaliza o Office e salva suas personalizações em um arquivo msp de personalização de Instalação. Você coloca o arquivo na pasta Atualizações no ponto de instalação de rede. Ao instalar o Office, a Instalação procura por um arquivo de personalização da Instalação na pasta Atualizações e aplica as personalizações. A pasta Atualizações pode ser usada somente para implantar atualizações de software durante uma instalação inicial do Office.
  
A OCT faz parte da configuração e só é usada para versões licenciadas por volume do produto. Você executa a OCT digitando `setup.exe /admin` na linha de comando da raiz do ponto de instalação da rede que contém os arquivos de origem do Office. Por exemplo, use o seguinte:
  
 ```console
\\server\share\Office15\setup.exe /admin
```
  
Os administradores usam a OCT para criar um arquivo de configuração de personalização. msp e podem personalizar as seguintes áreas:
  
- **Configurar** Usado para especificar o local de instalação padrão no cliente e o nome da organização padrão, origens adicionais de instalação de rede, chave do produto, contrato de licença de usuário final, nível de exibição, versões anteriores do Office para remover, programas personalizados para executar durante a instalação, configurações de segurança e propriedades de configuração.
    
- **Recursos** do Usado para definir as configurações do usuário e para personalizar como os recursos do Office são instalados. Os administradores podem usar o OCT para especificar os valores padrões iniciais das configurações do aplicativo do Office para usuários. Os usuários podem modificar a maioria das configurações após a instalação.
    
- **Conteúdo adicional** Usado para adicionar ou remover arquivos, adicionar ou remover entradas do registro e configurar atalhos.
    
- **Outlook** Usado para personalizar o perfil padrão do Outlook de um usuário, especificar as configurações do Exchange, adicionar contas, remover contas e exportar configurações e especificar grupos de Envio\recebimento.
    
Para obter informações sobre a OCT, consulte [usar a OCT para personalizar o Office 2013](https://docs.microsoft.com/previous-versions/office/office-2013-resource-kit/cc179132(v=office.15)). Observe que essas informações também se aplicam às versões posteriores do Office.
  

