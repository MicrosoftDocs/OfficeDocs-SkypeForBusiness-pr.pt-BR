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
ms.openlocfilehash: e7eb331c1b63a9e6a94ae3920e65ef57f426fbb0
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/07/2019
ms.locfileid: "36234597"
---
# <a name="use-the-office-customization-tool-oct-in-skype-for-business-server"></a><span data-ttu-id="72725-103">Usar a ferramenta de personalização do Office (OCT) no Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="72725-103">Use the Office Customization Tool (OCT) in Skype for Business Server</span></span>
 
<span data-ttu-id="72725-104">**Resumo:** Como usar a ferramenta de personalização do Office com o cliente Skype for Business.</span><span class="sxs-lookup"><span data-stu-id="72725-104">**Summary:** How to use the Office Customization Tool with the Skype for Business client.</span></span>
  
<span data-ttu-id="72725-105">O Office Customization Tool (OCT) faz parte do programa de Instalação e é a ferramenta recomendada para várias personalizações.</span><span class="sxs-lookup"><span data-stu-id="72725-105">The Office Customization Tool (OCT) is part of the Setup program and is the recommended tool for many customizations.</span></span> <span data-ttu-id="72725-106">Ao usar o OCT, você personaliza o Office e salva suas personalizações em um arquivo msp de personalização de Instalação.</span><span class="sxs-lookup"><span data-stu-id="72725-106">By using the OCT, you customize Office and save your customizations in a Setup customization .msp file.</span></span> <span data-ttu-id="72725-107">Você coloca o arquivo na pasta Atualizações no ponto de instalação de rede.</span><span class="sxs-lookup"><span data-stu-id="72725-107">You place the file in the Updates folder on the network installation point.</span></span> <span data-ttu-id="72725-108">Ao instalar o Office, a Instalação procura por um arquivo de personalização da Instalação na pasta Atualizações e aplica as personalizações.</span><span class="sxs-lookup"><span data-stu-id="72725-108">When you install Office, Setup looks for a Setup customization file in the Updates folder and applies the customizations.</span></span> <span data-ttu-id="72725-109">A pasta Atualizações pode ser usada somente para implantar atualizações de software durante uma instalação inicial do Office.</span><span class="sxs-lookup"><span data-stu-id="72725-109">The Updates folder can be used only to deploy software updates during an initial installation of Office.</span></span>
  
<span data-ttu-id="72725-110">A OCT faz parte da configuração e só é usada para versões licenciadas por volume do produto.</span><span class="sxs-lookup"><span data-stu-id="72725-110">The OCT is part of setup and it is only used for volume licensed versions of the product.</span></span> <span data-ttu-id="72725-111">Você executa a OCT digitando `setup.exe /admin` na linha de comando da raiz do ponto de instalação da rede que contém os arquivos de origem do Office.</span><span class="sxs-lookup"><span data-stu-id="72725-111">You run the OCT by typing  `setup.exe /admin` at the command line from the root of the network installation point that contains the Office source files.</span></span> <span data-ttu-id="72725-112">Por exemplo, use o seguinte:</span><span class="sxs-lookup"><span data-stu-id="72725-112">For example, use the following:</span></span>
  
 ```
\\server\share\Office15\setup.exe /admin
```
  
<span data-ttu-id="72725-113">Os administradores usam a OCT para criar um arquivo de configuração de personalização. msp e podem personalizar as seguintes áreas:</span><span class="sxs-lookup"><span data-stu-id="72725-113">Administrators use the OCT to create a setup customization .msp file and can customize the following areas:</span></span>
  
- <span data-ttu-id="72725-114">**Configurar** Usado para especificar o local de instalação padrão no cliente e o nome da organização padrão, origens adicionais de instalação de rede, chave do produto, contrato de licença de usuário final, nível de exibição, versões anteriores do Office para remover, programas personalizados a serem executados durante instalação, configurações de segurança e propriedades de configuração.</span><span class="sxs-lookup"><span data-stu-id="72725-114">**Setup** Used to specify default installation location on the client and default organization name, additional network installation sources, product key, end-user license agreement, display level, earlier versions of Office to remove, custom programs to run during installation, security settings, and Setup properties.</span></span>
    
- <span data-ttu-id="72725-115">**Recursos** do Usado para definir as configurações do usuário e para personalizar como os recursos do Office são instalados.</span><span class="sxs-lookup"><span data-stu-id="72725-115">**Features** Used to configure user settings and to customize how Office features are installed.</span></span> <span data-ttu-id="72725-116">Os administradores podem usar o OCT para especificar os valores padrões iniciais das configurações do aplicativo do Office para usuários.</span><span class="sxs-lookup"><span data-stu-id="72725-116">Administrators can use the OCT to specify initial default values of Office application settings for users.</span></span> <span data-ttu-id="72725-117">Os usuários podem modificar a maioria das configurações após a instalação.</span><span class="sxs-lookup"><span data-stu-id="72725-117">Users can modify most of the settings after the installation.</span></span>
    
- <span data-ttu-id="72725-118">**Conteúdo adicional** Usado para adicionar ou remover arquivos, adicionar ou remover entradas do registro e configurar atalhos.</span><span class="sxs-lookup"><span data-stu-id="72725-118">**Additional content** Used to add or remove files, add or remove registry entries, and configure shortcuts.</span></span>
    
- <span data-ttu-id="72725-119">**Outlook** Usado para personalizar o perfil padrão do Outlook de um usuário, especificar as configurações do Exchange, adicionar contas, remover contas e exportar configurações e especificar grupos de Envio\recebimento.</span><span class="sxs-lookup"><span data-stu-id="72725-119">**Outlook** Used to customize a user's default Outlook profile, specify Exchange settings, add accounts, remove accounts and export settings, and specify Send\Receive groups.</span></span>
    
<span data-ttu-id="72725-120">Para obter informações sobre a OCT, consulte [usar a OCT para personalizar o Office 2013](https://docs.microsoft.com/previous-versions/office/office-2013-resource-kit/cc179132(v=office.15)).</span><span class="sxs-lookup"><span data-stu-id="72725-120">For information about the OCT, see [Use the OCT to customize Office 2013](https://docs.microsoft.com/previous-versions/office/office-2013-resource-kit/cc179132(v=office.15)).</span></span> <span data-ttu-id="72725-121">Observe que essas informações também se aplicam às versões posteriores do Office.</span><span class="sxs-lookup"><span data-stu-id="72725-121">Note that this information also applies to later versions of Office.</span></span>
  

