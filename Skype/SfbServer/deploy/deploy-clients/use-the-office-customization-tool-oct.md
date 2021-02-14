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
# <a name="use-the-office-customization-tool-oct-in-skype-for-business-server"></a><span data-ttu-id="702f8-103">Usar a Ferramenta de Personalização do Office (OCT) no Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="702f8-103">Use the Office Customization Tool (OCT) in Skype for Business Server</span></span>
 
<span data-ttu-id="702f8-104">**Resumo:** Como usar a Ferramenta de Personalização do Office com o cliente Skype for Business.</span><span class="sxs-lookup"><span data-stu-id="702f8-104">**Summary:** How to use the Office Customization Tool with the Skype for Business client.</span></span>
  
<span data-ttu-id="702f8-105">A Ferramenta de Personalização do Office (OCT) faz parte do programa de Instalação e é a ferramenta recomendada para muitas personalizações.</span><span class="sxs-lookup"><span data-stu-id="702f8-105">The Office Customization Tool (OCT) is part of the Setup program and is the recommended tool for many customizations.</span></span> <span data-ttu-id="702f8-106">Usando a OCT, você personaliza o Office e salva suas personalizações em um arquivo .msp de personalização da Instalação.</span><span class="sxs-lookup"><span data-stu-id="702f8-106">By using the OCT, you customize Office and save your customizations in a Setup customization .msp file.</span></span> <span data-ttu-id="702f8-107">Coloque o arquivo na pasta Atualizações no ponto de instalação na rede.</span><span class="sxs-lookup"><span data-stu-id="702f8-107">You place the file in the Updates folder on the network installation point.</span></span> <span data-ttu-id="702f8-108">Quando você instala o Office, a Instalação procura um arquivo de personalização da Instalação na pasta Atualizações e aplica as personalizações.</span><span class="sxs-lookup"><span data-stu-id="702f8-108">When you install Office, Setup looks for a Setup customization file in the Updates folder and applies the customizations.</span></span> <span data-ttu-id="702f8-109">A pasta Atualizações só pode ser usada para implantar atualizações de software durante uma instalação inicial do Office.</span><span class="sxs-lookup"><span data-stu-id="702f8-109">The Updates folder can be used only to deploy software updates during an initial installation of Office.</span></span>
  
<span data-ttu-id="702f8-110">A OCT faz parte da instalação e só é usada para versões licenciadas por volume do produto.</span><span class="sxs-lookup"><span data-stu-id="702f8-110">The OCT is part of setup and it is only used for volume licensed versions of the product.</span></span> <span data-ttu-id="702f8-111">Execute a OCT digitando na linha de comando a partir da raiz do ponto de instalação na rede que  `setup.exe /admin` contém os arquivos de origem do Office.</span><span class="sxs-lookup"><span data-stu-id="702f8-111">You run the OCT by typing  `setup.exe /admin` at the command line from the root of the network installation point that contains the Office source files.</span></span> <span data-ttu-id="702f8-112">Por exemplo, use o seguinte:</span><span class="sxs-lookup"><span data-stu-id="702f8-112">For example, use the following:</span></span>
  
 ```console
\\server\share\Office15\setup.exe /admin
```
  
<span data-ttu-id="702f8-113">Os administradores usam a OCT para criar um arquivo .msp de personalização da instalação e podem personalizar as seguintes áreas:</span><span class="sxs-lookup"><span data-stu-id="702f8-113">Administrators use the OCT to create a setup customization .msp file and can customize the following areas:</span></span>
  
- <span data-ttu-id="702f8-114">**Instalação** Usado para especificar o local de instalação padrão no nome da organização padrão e do cliente, fontes de instalação de rede adicionais, chave do produto, contrato de licença do usuário final, nível de exibição, versões anteriores do Office a remover, programas personalizados para executar durante a instalação, configurações de segurança e propriedades de Instalação.</span><span class="sxs-lookup"><span data-stu-id="702f8-114">**Setup** Used to specify default installation location on the client and default organization name, additional network installation sources, product key, end-user license agreement, display level, earlier versions of Office to remove, custom programs to run during installation, security settings, and Setup properties.</span></span>
    
- <span data-ttu-id="702f8-115">**Recursos** Usado para definir as configurações do usuário e personalizar como os recursos do Office são instalados.</span><span class="sxs-lookup"><span data-stu-id="702f8-115">**Features** Used to configure user settings and to customize how Office features are installed.</span></span> <span data-ttu-id="702f8-116">Os administradores podem usar a OCT para especificar valores padrão iniciais das configurações do aplicativo do Office para os usuários.</span><span class="sxs-lookup"><span data-stu-id="702f8-116">Administrators can use the OCT to specify initial default values of Office application settings for users.</span></span> <span data-ttu-id="702f8-117">Os usuários podem modificar a maioria das configurações após a instalação.</span><span class="sxs-lookup"><span data-stu-id="702f8-117">Users can modify most of the settings after the installation.</span></span>
    
- <span data-ttu-id="702f8-118">**Conteúdo adicional** Usado para adicionar ou remover arquivos, adicionar ou remover entradas do Registro e configurar atalhos.</span><span class="sxs-lookup"><span data-stu-id="702f8-118">**Additional content** Used to add or remove files, add or remove registry entries, and configure shortcuts.</span></span>
    
- <span data-ttu-id="702f8-119">**Outlook** Usado para personalizar o perfil padrão do Outlook de um usuário, especificar configurações do Exchange, adicionar contas, remover contas e exportar configurações e especificar grupos de Envio/Recebimento.</span><span class="sxs-lookup"><span data-stu-id="702f8-119">**Outlook** Used to customize a user's default Outlook profile, specify Exchange settings, add accounts, remove accounts and export settings, and specify Send\Receive groups.</span></span>
    
<span data-ttu-id="702f8-120">Para obter informações sobre a OCT, [consulte Usar a OCT para personalizar o Office 2013.](https://docs.microsoft.com/previous-versions/office/office-2013-resource-kit/cc179132(v=office.15))</span><span class="sxs-lookup"><span data-stu-id="702f8-120">For information about the OCT, see [Use the OCT to customize Office 2013](https://docs.microsoft.com/previous-versions/office/office-2013-resource-kit/cc179132(v=office.15)).</span></span> <span data-ttu-id="702f8-121">Observe que essas informações também se aplicarão a versões posteriores do Office.</span><span class="sxs-lookup"><span data-stu-id="702f8-121">Note that this information also applies to later versions of Office.</span></span>
  

