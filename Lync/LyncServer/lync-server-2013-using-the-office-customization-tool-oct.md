---
title: 'Lync Server 2013: usando a ferramenta de personalização do Office (OCT)'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Using the Office Customization Tool (OCT)
ms:assetid: 26647cb6-ba84-4ba7-8b6f-2cf86818e530
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204748(v=OCS.15)
ms:contentKeyID: 48183654
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c55cfa8fd795feeca5e265f43823c4263512211f
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42212547"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="using-the-office-customization-tool-oct-in-lync-server-2013"></a><span data-ttu-id="7bb97-102">Usando a ferramenta de personalização do Office (OCT) no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="7bb97-102">Using the Office Customization Tool (OCT) in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="7bb97-103">_**Última modificação do tópico:** 2012-10-02_</span><span class="sxs-lookup"><span data-stu-id="7bb97-103">_**Topic Last Modified:** 2012-10-02_</span></span>

<span data-ttu-id="7bb97-104">A OCT (ferramenta de personalização do Office) faz parte do programa de instalação e é a ferramenta recomendada para várias personalizações.</span><span class="sxs-lookup"><span data-stu-id="7bb97-104">The Office Customization Tool (OCT) is part of the Setup program and is the recommended tool for many customizations.</span></span> <span data-ttu-id="7bb97-105">Usando a OCT, você personaliza o Office e salva suas personalizações em um arquivo de personalização de instalação. msp.</span><span class="sxs-lookup"><span data-stu-id="7bb97-105">By using the OCT, you customize Office and save your customizations in a Setup customization .msp file.</span></span> <span data-ttu-id="7bb97-106">Coloque o arquivo na pasta Atualizações no ponto de instalação na rede.</span><span class="sxs-lookup"><span data-stu-id="7bb97-106">You place the file in the Updates folder on the network installation point.</span></span> <span data-ttu-id="7bb97-107">Quando você instala o Office, a instalação procura um arquivo de personalização da instalação na pasta Atualizações e aplica as personalizações.</span><span class="sxs-lookup"><span data-stu-id="7bb97-107">When you install Office, Setup looks for a Setup customization file in the Updates folder and applies the customizations.</span></span> <span data-ttu-id="7bb97-108">A pasta Atualizações pode ser usada apenas para implantar atualizações de software durante uma instalação inicial do Office 2013.</span><span class="sxs-lookup"><span data-stu-id="7bb97-108">The Updates folder can be used only to deploy software updates during an initial installation of Office 2013.</span></span>

<span data-ttu-id="7bb97-109">A OCT é parte da configuração e está incluída nas versões de licença de volume do produto.</span><span class="sxs-lookup"><span data-stu-id="7bb97-109">The OCT is part of setup and it is included in volume license versions of the product.</span></span> <span data-ttu-id="7bb97-110">Você executa a OCT digitando `setup.exe /admin` na linha de comando a partir da raiz do ponto de instalação de rede que contém os arquivos de origem do Office 2013.</span><span class="sxs-lookup"><span data-stu-id="7bb97-110">You run the OCT by typing `setup.exe /admin` at the command line from the root of the network installation point that contains the Office 2013 source files.</span></span> <span data-ttu-id="7bb97-111">Por exemplo, use o seguinte:</span><span class="sxs-lookup"><span data-stu-id="7bb97-111">For example, use the following:</span></span>

`\\server\share\Office15\setup.exe /admin`

<span data-ttu-id="7bb97-112">Os administradores usam a OCT para criar um arquivo de personalização de instalação. msp.</span><span class="sxs-lookup"><span data-stu-id="7bb97-112">Administrators use the OCT to create a setup customization .msp file.</span></span> <span data-ttu-id="7bb97-113">Como no Microsoft Office 2010 OCT, os administradores podem personalizar as seguintes áreas:</span><span class="sxs-lookup"><span data-stu-id="7bb97-113">As in the Microsoft Office 2010 OCT, administrators can customize the following areas:</span></span>

  - <span data-ttu-id="7bb97-114">**Configuração** Usado para especificar o local de instalação padrão no cliente e o nome da organização padrão, fontes de instalação de rede adicionais, chave de produto, contrato de licença de usuário final, nível de exibição, versões anteriores do Office para remover, programas personalizados para executar durante a instalação, configurações de segurança e propriedades de instalação.</span><span class="sxs-lookup"><span data-stu-id="7bb97-114">**Setup** Used to specify default installation location on the client and default organization name, additional network installation sources, product key, end-user license agreement, display level, earlier versions of Office to remove, custom programs to run during installation, security settings, and Setup properties.</span></span>

  - <span data-ttu-id="7bb97-115">**Recursos** do Usado para definir as configurações do usuário e para personalizar como os recursos do Office são instalados.</span><span class="sxs-lookup"><span data-stu-id="7bb97-115">**Features** Used to configure user settings and to customize how Office features are installed.</span></span> <span data-ttu-id="7bb97-116">Os administradores podem usar a OCT para especificar os valores padrão iniciais das configurações de aplicativo do Office para os usuários.</span><span class="sxs-lookup"><span data-stu-id="7bb97-116">Administrators can use the OCT to specify initial default values of Office application settings for users.</span></span> <span data-ttu-id="7bb97-117">Os usuários podem modificar a maioria das configurações após a instalação.</span><span class="sxs-lookup"><span data-stu-id="7bb97-117">Users can modify most of the settings after the installation.</span></span>

  - <span data-ttu-id="7bb97-118">**Conteúdo adicional** Usado para adicionar ou remover arquivos, adicionar ou remover entradas do registro e configurar atalhos.</span><span class="sxs-lookup"><span data-stu-id="7bb97-118">**Additional content** Used to add or remove files, add or remove registry entries, and configure shortcuts.</span></span>

  - <span data-ttu-id="7bb97-119">**Outlook** Usado para personalizar o perfil padrão do Outlook do usuário, especificar as configurações do Exchange, adicionar contas, remover contas e exportar configurações e\\especificar grupos de recebimento de envio.</span><span class="sxs-lookup"><span data-stu-id="7bb97-119">**Outlook** Used to customize a user's default Outlook profile, specify Exchange settings, add accounts, remove accounts and export settings, and specify Send\\Receive groups.</span></span>

<span data-ttu-id="7bb97-120">Para obter informações sobre a OCT, <https://go.microsoft.com/fwlink/p/?linkid=267516>consulte.</span><span class="sxs-lookup"><span data-stu-id="7bb97-120">For information about the OCT, see <https://go.microsoft.com/fwlink/p/?linkid=267516>.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

