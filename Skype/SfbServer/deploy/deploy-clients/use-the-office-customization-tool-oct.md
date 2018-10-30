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
ms.sourcegitcommit: 7d65eafd5b0163ece91deb7801458c7a45fcc4f7
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/29/2018
ms.locfileid: "25838662"
---
# <a name="use-the-office-customization-tool-oct-in-skype-for-business-server"></a><span data-ttu-id="db23f-103">Usar a ferramenta de personalização do Office (OCT) no Skype para Business Server</span><span class="sxs-lookup"><span data-stu-id="db23f-103">Use the Office Customization Tool (OCT) in Skype for Business Server</span></span>
 
<span data-ttu-id="db23f-104">**Resumo:** Como usar a ferramenta de personalização do Office com o Skype para o cliente de negócios.</span><span class="sxs-lookup"><span data-stu-id="db23f-104">**Summary:** How to use the Office Customization Tool with the Skype for Business client.</span></span>
  
<span data-ttu-id="db23f-105">O Office Customization Tool (OCT) faz parte do programa de Instalação e é a ferramenta recomendada para várias personalizações.</span><span class="sxs-lookup"><span data-stu-id="db23f-105">The Office Customization Tool (OCT) is part of the Setup program and is the recommended tool for many customizations.</span></span> <span data-ttu-id="db23f-106">Ao usar o OCT, você personaliza o Office e salva suas personalizações em um arquivo msp de personalização de Instalação.</span><span class="sxs-lookup"><span data-stu-id="db23f-106">By using the OCT, you customize Office and save your customizations in a Setup customization .msp file.</span></span> <span data-ttu-id="db23f-107">Você coloca o arquivo na pasta Atualizações no ponto de instalação de rede.</span><span class="sxs-lookup"><span data-stu-id="db23f-107">You place the file in the Updates folder on the network installation point.</span></span> <span data-ttu-id="db23f-108">Ao instalar o Office, a Instalação procura por um arquivo de personalização da Instalação na pasta Atualizações e aplica as personalizações.</span><span class="sxs-lookup"><span data-stu-id="db23f-108">When you install Office, Setup looks for a Setup customization file in the Updates folder and applies the customizations.</span></span> <span data-ttu-id="db23f-109">Pasta de atualizações pode ser usada apenas para implantar atualizações de software durante uma instalação inicial do Office.</span><span class="sxs-lookup"><span data-stu-id="db23f-109">The Updates folder can be used only to deploy software updates during an initial installation of Office.</span></span>
  
<span data-ttu-id="db23f-110">A OCT é parte da instalação e ele é usado apenas para as versões do produto de licença de volume.</span><span class="sxs-lookup"><span data-stu-id="db23f-110">The OCT is part of setup and it is only used for volume licensed versions of the product.</span></span> <span data-ttu-id="db23f-111">Executar a OCT digitando `setup.exe /admin` na linha de comando a partir da raiz do ponto de instalação de rede que contém o escritório arquivos de origem.</span><span class="sxs-lookup"><span data-stu-id="db23f-111">You run the OCT by typing  `setup.exe /admin` at the command line from the root of the network installation point that contains the Office source files.</span></span> <span data-ttu-id="db23f-112">Por exemplo, use o seguinte:</span><span class="sxs-lookup"><span data-stu-id="db23f-112">For example, use the following:</span></span>
  
 ```
\\server\share\Office15\setup.exe /admin
```
  
<span data-ttu-id="db23f-113">Os administradores usam a OCT para criar um arquivo. msp de personalização de instalação e pode personalizar as seguintes áreas:</span><span class="sxs-lookup"><span data-stu-id="db23f-113">Administrators use the OCT to create a setup customization .msp file and can customize the following areas:</span></span>
  
- <span data-ttu-id="db23f-114">**Programa de instalação** Usado para especificar o local de instalação padrão no cliente e o padrão de nome de organização, fontes de instalação de rede adicionais, chave de produto, contrato de licença de usuário final, exibir versões anteriores, de nível do Office para remover, programas personalizados a serem executados durante instalação, as configurações de segurança e propriedades de instalação.</span><span class="sxs-lookup"><span data-stu-id="db23f-114">**Setup** Used to specify default installation location on the client and default organization name, additional network installation sources, product key, end-user license agreement, display level, earlier versions of Office to remove, custom programs to run during installation, security settings, and Setup properties.</span></span>
    
- <span data-ttu-id="db23f-115">**Recursos** Usado para definir configurações de usuário e personalizar como os recursos do Office são instalados.</span><span class="sxs-lookup"><span data-stu-id="db23f-115">**Features** Used to configure user settings and to customize how Office features are installed.</span></span> <span data-ttu-id="db23f-116">Os administradores podem usar o OCT para especificar os valores padrões iniciais das configurações do aplicativo do Office para usuários.</span><span class="sxs-lookup"><span data-stu-id="db23f-116">Administrators can use the OCT to specify initial default values of Office application settings for users.</span></span> <span data-ttu-id="db23f-117">Os usuários podem modificar a maioria das configurações após a instalação.</span><span class="sxs-lookup"><span data-stu-id="db23f-117">Users can modify most of the settings after the installation.</span></span>
    
- <span data-ttu-id="db23f-118">**Conteúdo adicional** Usado para adicionar ou remover arquivos, adicionar ou remover entradas do registro e configurar atalhos.</span><span class="sxs-lookup"><span data-stu-id="db23f-118">**Additional content** Used to add or remove files, add or remove registry entries, and configure shortcuts.</span></span>
    
- <span data-ttu-id="db23f-119">**Outlook** Usado para personalizar o perfil padrão do Outlook do usuário, especificar configurações do Exchange, adicionar contas, remover contas e exportar configurações e especificar grupos de envio/recebimento.</span><span class="sxs-lookup"><span data-stu-id="db23f-119">**Outlook** Used to customize a user's default Outlook profile, specify Exchange settings, add accounts, remove accounts and export settings, and specify Send\Receive groups.</span></span>
    
<span data-ttu-id="db23f-120">Para obter informações sobre a OCT, consulte [usar a OCT para personalizar o Office 2013](https://docs.microsoft.com/previous-versions/office/office-2013-resource-kit/cc179132(v=office.15)).</span><span class="sxs-lookup"><span data-stu-id="db23f-120">For information about the OCT, see [Use the OCT to customize Office 2013](https://docs.microsoft.com/previous-versions/office/office-2013-resource-kit/cc179132(v=office.15)).</span></span> <span data-ttu-id="db23f-121">Observe que essas informações também se aplicam às versões posteriores do Office.</span><span class="sxs-lookup"><span data-stu-id="db23f-121">Note that this information also applies to later versions of Office.</span></span>
  

