---
title: Usar a ferramenta de personalização do Office (OCT) no Skype para Business Server
ms.author: chucked
author: chuckedmonson
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 26647cb6-ba84-4ba7-8b6f-2cf86818e530
description: 'Resumo: Como usar a ferramenta de personalização do Office com o Skype para o cliente de negócios.'
ms.openlocfilehash: 6050a9e9c36fa62aff16994469e63a9689ab5958
ms.sourcegitcommit: 30620021ceba916a505437ab641a23393f55827a
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/15/2018
ms.locfileid: "26530675"
---
# <a name="use-the-office-customization-tool-oct-in-skype-for-business-server"></a>Usar a ferramenta de personalização do Office (OCT) no Skype para Business Server
 
**Resumo:** Como usar a ferramenta de personalização do Office com o Skype para o cliente de negócios.
  
O Office Customization Tool (OCT) faz parte do programa de Instalação e é a ferramenta recomendada para várias personalizações. Ao usar o OCT, você personaliza o Office e salva suas personalizações em um arquivo msp de personalização de Instalação. Você coloca o arquivo na pasta Atualizações no ponto de instalação de rede. Ao instalar o Office, a Instalação procura por um arquivo de personalização da Instalação na pasta Atualizações e aplica as personalizações. Pasta de atualizações pode ser usada apenas para implantar atualizações de software durante uma instalação inicial do Office.
  
A OCT é parte da instalação e ele é usado apenas para as versões do produto de licença de volume. Executar a OCT digitando `setup.exe /admin` na linha de comando a partir da raiz do ponto de instalação de rede que contém o escritório arquivos de origem. Por exemplo, use o seguinte:
  
 ```
\\server\share\Office15\setup.exe /admin
```
  
Os administradores usam a OCT para criar um arquivo. msp de personalização de instalação e pode personalizar as seguintes áreas:
  
- **Programa de instalação** Usado para especificar o local de instalação padrão no cliente e o padrão de nome de organização, fontes de instalação de rede adicionais, chave de produto, contrato de licença de usuário final, exibir versões anteriores, de nível do Office para remover, programas personalizados a serem executados durante instalação, as configurações de segurança e propriedades de instalação.
    
- **Recursos** Usado para definir configurações de usuário e personalizar como os recursos do Office são instalados. Os administradores podem usar o OCT para especificar os valores padrões iniciais das configurações do aplicativo do Office para usuários. Os usuários podem modificar a maioria das configurações após a instalação.
    
- **Conteúdo adicional** Usado para adicionar ou remover arquivos, adicionar ou remover entradas do registro e configurar atalhos.
    
- **Outlook** Usado para personalizar o perfil padrão do Outlook do usuário, especificar configurações do Exchange, adicionar contas, remover contas e exportar configurações e especificar grupos de envio/recebimento.
    
Para obter informações sobre a OCT, consulte [usar a OCT para personalizar o Office 2013](https://docs.microsoft.com/previous-versions/office/office-2013-resource-kit/cc179132(v=office.15)). Observe que essas informações também se aplicam às versões posteriores do Office.
  

