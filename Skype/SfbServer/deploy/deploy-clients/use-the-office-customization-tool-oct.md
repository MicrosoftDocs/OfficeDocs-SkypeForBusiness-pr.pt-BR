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
# <a name="use-the-office-customization-tool-oct-in-skype-for-business-server-2015"></a><span data-ttu-id="53afc-103">Usar a OCT (Ferramenta de Personalização do Office) no Skype for Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="53afc-103">Use the Office Customization Tool (OCT) in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="53afc-104">Resumo: como usar a Ferramenta de Personalização do Office com o cliente .</span><span class="sxs-lookup"><span data-stu-id="53afc-104">Summary: how to use the Office Customization Tool  with the  client.</span></span>
  
<span data-ttu-id="53afc-105">O Office Customization Tool (OCT) faz parte do programa de Instalação e é a ferramenta recomendada para várias personalizações.</span><span class="sxs-lookup"><span data-stu-id="53afc-105">The Office Customization Tool (OCT) is part of the Setup program and is the recommended tool for many customizations.</span></span> <span data-ttu-id="53afc-106">Ao usar o OCT, você personaliza o Office e salva suas personalizações em um arquivo msp de personalização de Instalação.</span><span class="sxs-lookup"><span data-stu-id="53afc-106">By using the OCT, you customize Office and save your customizations in a Setup customization .msp file.</span></span> <span data-ttu-id="53afc-107">Você coloca o arquivo na pasta Atualizações no ponto de instalação de rede.</span><span class="sxs-lookup"><span data-stu-id="53afc-107">You place the file in the Updates folder on the network installation point.</span></span> <span data-ttu-id="53afc-108">Ao instalar o Office, a Instalação procura por um arquivo de personalização da Instalação na pasta Atualizações e aplica as personalizações.</span><span class="sxs-lookup"><span data-stu-id="53afc-108">When you install Office, Setup looks for a Setup customization file in the Updates folder and applies the customizations.</span></span> <span data-ttu-id="53afc-109">A pasta Atualização pode ser usada apenas para implantar atualizações de software durante a instalação inicial do .</span><span class="sxs-lookup"><span data-stu-id="53afc-109">The Updates folder can be used only to deploy software updates during an initial installation of .</span></span>
  
<span data-ttu-id="53afc-110">O OCT faz parte da instalação e está incluído em versões de licença de volume do produto.</span><span class="sxs-lookup"><span data-stu-id="53afc-110">The OCT is part of setup and it is included in volume license versions of the product.</span></span> <span data-ttu-id="53afc-111">Você executa o OCT digitando  na linha de comando na raiz do ponto de instalação de rede que contém os arquivos de origem do .</span><span class="sxs-lookup"><span data-stu-id="53afc-111">You run the OCT by typing  at the command line from the root of the network installation point that contains the  source files.</span></span> <span data-ttu-id="53afc-112">Por exemplo, use o seguinte:</span><span class="sxs-lookup"><span data-stu-id="53afc-112">For example, use the following:</span></span>
  
 `\\server\share\Office15\setup.exe /admin`
  
<span data-ttu-id="53afc-113">Os administradores usam o OCT para criar um arquivo .msp de personalização da instalação. Como no OCT do , os administradores podem personalizar as seguintes áreas:</span><span class="sxs-lookup"><span data-stu-id="53afc-113">Administrators use the OCT to create a setup customization .msp file. As in the  OCT, administrators can customize the following areas:</span></span>
  
- <span data-ttu-id="53afc-114">**Instalação** Usado para especificar o local de instalação padrão no nome da organização padrão e cliente, fontes de instalação de rede adicionais, chave do produto, contrato de licença do usuário final, nível de exibição, versões anteriores do Office para remover, programas personalizados para executar durante a instalação, configurações de segurança e propriedades de Instalação.</span><span class="sxs-lookup"><span data-stu-id="53afc-114">**Setup**   Used to specify default installation location on the client and default organization name, additional network installation sources, product key, end-user license agreement, display level, earlier versions of Office to remove, custom programs to run during installation, security settings, and Setup properties.</span></span>
    
- <span data-ttu-id="53afc-115">Usado para definir as configurações do usuário e personalizar como os recursos do Office são instalados.</span><span class="sxs-lookup"><span data-stu-id="53afc-115">Used to configure user settings and to customize how Office features are installed.</span></span> <span data-ttu-id="53afc-116">Os administradores podem usar o OCT para especificar os valores padrões iniciais das configurações do aplicativo do Office para usuários.</span><span class="sxs-lookup"><span data-stu-id="53afc-116">Administrators can use the OCT to specify initial default values of Office application settings for users.</span></span> <span data-ttu-id="53afc-117">Os usuários podem modificar a maioria das configurações após a instalação.</span><span class="sxs-lookup"><span data-stu-id="53afc-117">Users can modify most of the settings after the installation.</span></span>
    
- <span data-ttu-id="53afc-118">**Conteúdo adicional** Usado para adicionar ou remover arquivos, adicionar ou remover entradas do Registro e configurar atalhos.</span><span class="sxs-lookup"><span data-stu-id="53afc-118">**Additional content**   Used to add or remove files, add or remove registry entries, and configure shortcuts.</span></span>
    
- <span data-ttu-id="53afc-119">**Outlook** Usado para personalizar o perfil padrão do Outlook do usuário, especificar as configurações do Exchange, adicionar contas, remover contas, exportar configurações e especificar grupos de Envio/Recebimento.</span><span class="sxs-lookup"><span data-stu-id="53afc-119">**Outlook**   Used to customize a user's default Outlook profile, specify Exchange settings, add accounts, remove accounts and export settings, and specify Send\Receive groups.</span></span>
    
<span data-ttu-id="53afc-120">For information about the OCT, see [Use the OCT to customize Office 2013](https://technet.microsoft.com/library/cc179132.aspx).</span><span class="sxs-lookup"><span data-stu-id="53afc-120">For information about the OCT, see [Use the OCT to customize Office 2013](https://technet.microsoft.com/library/cc179132.aspx).</span></span> <span data-ttu-id="53afc-121">Note that this information also applies to Office 2016.</span><span class="sxs-lookup"><span data-stu-id="53afc-121">Note that this information also applies to Office 2016.</span></span>
  

