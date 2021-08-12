---
title: Use a Office de Personalização (OCT) em Skype for Business Server
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
ms.assetid: 26647cb6-ba84-4ba7-8b6f-2cf86818e530
description: 'Resumo: como usar a ferramenta de personalização Office com o cliente Skype for Business cliente.'
ms.openlocfilehash: 383db7b623790153114740c4d245823c38ec63c5881842c281e6c10f7834a450
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/05/2021
ms.locfileid: "54294918"
---
# <a name="use-the-office-customization-tool-oct-in-skype-for-business-server"></a>Use a Office de Personalização (OCT) em Skype for Business Server
 
**Resumo:** Como usar a ferramenta Office personalização com o cliente Skype for Business cliente.
  
A Office de Personalização (OCT) faz parte do programa de Instalação e é a ferramenta recomendada para muitas personalizações. Usando a OCT, você personaliza Office e salva suas personalizações em um arquivo .msp de personalização da Instalação. Você coloca o arquivo na pasta Atualizações no ponto de instalação da rede. Ao instalar o Office, a Instalação procura um arquivo de personalização da Instalação na pasta Atualizações e aplica as personalizações. A pasta Atualizações só pode ser usada para implantar atualizações de software durante uma instalação inicial do Office.
  
A OCT faz parte da instalação e só é usada para versões licenciadas por volume do produto. Execute a OCT digitando na linha de comando na raiz do ponto de instalação da rede que contém os arquivos de origem Office `setup.exe /admin` de origem. Por exemplo, use o seguinte:
  
 ```console
\\server\share\Office15\setup.exe /admin
```
  
Os administradores usam a OCT para criar um arquivo .msp de personalização de instalação e podem personalizar as seguintes áreas:
  
- **Instalação** Usado para especificar o local de instalação padrão no nome do cliente e da organização padrão, fontes de instalação de rede adicionais, chave do produto, contrato de licença do usuário final, nível de exibição, versões anteriores do Office para remover, programas personalizados a ser executados durante a instalação, configurações de segurança e propriedades de Instalação.
    
- **Recursos** Usado para definir as configurações do usuário e para personalizar como Office recursos são instalados. Os administradores podem usar a OCT para especificar valores padrão iniciais Office de aplicativos para usuários. Os usuários podem modificar a maioria das configurações após a instalação.
    
- **Conteúdo adicional** Usado para adicionar ou remover arquivos, adicionar ou remover entradas do Registro e configurar atalhos.
    
- **Outlook** Usado para personalizar o perfil padrão do usuário Outlook, especificar Exchange configurações, adicionar contas, remover contas e exportar configurações e especificar grupos Enviar\Receber.
    
Para obter informações sobre a OCT, consulte [Use the OCT to customize Office 2013](/previous-versions/office/office-2013-resource-kit/cc179132(v=office.15)). Observe que essas informações também se aplica a versões posteriores Office.
