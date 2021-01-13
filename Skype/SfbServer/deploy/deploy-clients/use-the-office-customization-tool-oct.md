---
title: Usar a Ferramenta de Personalização do Office (OCT) no Skype for Business Server
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
description: 'Resumo: Como usar a Ferramenta de Personalização do Office com o cliente Skype for Business.'
ms.openlocfilehash: ba99f0556f3fb1d0e0f6870d1eaa7a3d2108b4d4
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49812561"
---
# <a name="use-the-office-customization-tool-oct-in-skype-for-business-server"></a>Usar a Ferramenta de Personalização do Office (OCT) no Skype for Business Server
 
**Resumo:** Como usar a Ferramenta de Personalização do Office com o cliente Skype for Business.
  
A Ferramenta de Personalização do Office (OCT) faz parte do programa de Instalação e é a ferramenta recomendada para muitas personalizações. Usando a OCT, você personaliza o Office e salva suas personalizações em um arquivo .msp de personalização da Instalação. Coloque o arquivo na pasta Atualizações no ponto de instalação na rede. Quando você instala o Office, a Instalação procura um arquivo de personalização da Instalação na pasta Atualizações e aplica as personalizações. A pasta Atualizações só pode ser usada para implantar atualizações de software durante uma instalação inicial do Office.
  
A OCT faz parte da instalação e só é usada para versões licenciadas por volume do produto. Execute a OCT digitando na linha de comando a partir da raiz do ponto de instalação na rede que  `setup.exe /admin` contém os arquivos de origem do Office. Por exemplo, use o seguinte:
  
 ```console
\\server\share\Office15\setup.exe /admin
```
  
Os administradores usam a OCT para criar um arquivo .msp de personalização da instalação e podem personalizar as seguintes áreas:
  
- **Instalação** Usado para especificar o local de instalação padrão no nome da organização padrão e do cliente, fontes de instalação de rede adicionais, chave do produto, contrato de licença do usuário final, nível de exibição, versões anteriores do Office a remover, programas personalizados para executar durante a instalação, configurações de segurança e propriedades de Instalação.
    
- **Recursos** Usado para definir as configurações do usuário e personalizar como os recursos do Office são instalados. Os administradores podem usar a OCT para especificar valores padrão iniciais das configurações do aplicativo do Office para os usuários. Os usuários podem modificar a maioria das configurações após a instalação.
    
- **Conteúdo adicional** Usado para adicionar ou remover arquivos, adicionar ou remover entradas do Registro e configurar atalhos.
    
- **Outlook** Usado para personalizar o perfil padrão do Outlook de um usuário, especificar configurações do Exchange, adicionar contas, remover contas e exportar configurações e especificar grupos de Envio/Recebimento.
    
Para obter informações sobre a OCT, [consulte Usar a OCT para personalizar o Office 2013.](https://docs.microsoft.com/previous-versions/office/office-2013-resource-kit/cc179132(v=office.15)) Observe que essas informações também se aplicarão a versões posteriores do Office.
  

