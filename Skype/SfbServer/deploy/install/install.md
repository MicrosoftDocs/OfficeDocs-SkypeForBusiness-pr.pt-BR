---
title: Instalar o Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 7/14/2018
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.custom: Strat_SB_Admin
ms.assetid: 71299b34-8783-4384-9949-0d3162c8a36e
description: 'Resumo: saiba como preparar seu ambiente para uma instalação do Skype for Business Server. Baixe uma avaliação gratuita do Skype for Business Server no centro de avaliação da Microsoft em https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server:.'
ms.openlocfilehash: e33e773abf25be92c163de259af0c3f47e0b1783
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42042378"
---
# <a name="install-skype-for-business-server"></a>Instalar o Skype for Business Server
 
**Resumo:** Saiba como preparar seu ambiente para uma instalação do Skype for Business Server. Baixe uma avaliação gratuita do Skype for Business Server no centro de avaliação da Microsoft em[https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server](https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server):.
  
Este artigo apresenta uma instalação de exemplo do Skype for Business Server. Este artigo não tenta abranger todos os procedimentos necessários para executar uma instalação completa do Skype for Business Server. O objetivo é fornecer exemplos de procedimentos em uma topologia definida com restrição que inclua a funcionalidade básica de reunião e compartilhamento.
  
## <a name="overview-of-the-install-process-for-skype-for-business-server"></a>Visão geral do processo de instalação do Skype for Business Server

Uma instalação do Skype for Business Server inclui vários procedimentos diferentes. Os procedimentos necessários para obter o Skype for Business Server em execução em seu ambiente dependem das especificações do seu ambiente. Por exemplo, se você estiver usando o Windows Server para DNS, será beneficiado do procedimento de exemplo para adicionar uma entrada de DNS. Se você usar outro sistema para DNS, precisará seguir os procedimentos para o seu sistema DNS específico. Isso se aplica a muitos dos procedimentos desta seção.
  
O Skype for Business Server está disponível no Standard Edition e no Enterprise Edition. A principal diferença é que a edição Standard não é compatível com os recursos de alta disponibilidade incluídos na Enterprise Edition. 
  
O Skype for Business Server é um produto avançado e o processo de instalação exato depende de uma ótima dose de suas circunstâncias específicas. Esta seção descreve as etapas gerais para instalar o produto. No entanto, cada procedimento pode ser diferente dependendo do seu ambiente e das decisões de planejamento. Por exemplo, para pequenas organizações, um único servidor executando o Skype for Business Server Standard Edition pode ser apropriado, enquanto uma grande organização multinacional pode ter 50 servidores em locais em todo o mundo dedicado ao produto.
  
> [!NOTE]
> Para saber mais sobre as atualizações cumulativas mais recentes, consulte [atualizações para o Skype for Business Server](https://support.microsoft.com/kb/3061064). Após instalar o patch do CU1, um administrador precisa executar `Update-CsAdminRole` o cmdlet. Este cmdlet é necessário para acessar os novos cmdlets do GCP sobre o PowerShell remoto.
  
> [!IMPORTANT]
> Os procedimentos desta seção servem como um exemplo usando um conjunto de requisitos definido de forma estreita e presumir decisões específicas já foram feitas. Os procedimentos reais necessários para instalar o Skype for Business Server provavelmente serão muito diferentes. Use os procedimentos desta seção como um exemplo somente e não como um guia passo a passo para instalar o Skype for Business Server em todos os ambientes. 
  
Obter o Skype for Business Server em execução pela primeira vez envolve oito etapas principais. Você deve entender que os procedimentos de exemplo nesta seção não são os únicos procedimentos necessários para instalar o Skype for Business Server. As oito etapas a seguir são exemplos simples para ajudá-lo a entender melhor o processo geral e a obter um ambiente de trabalho básico em funcionamento. Você pode executar as etapas 1 a 5 em qualquer ordem. No entanto, você deve executar as etapas 6, 7 e 8 em ordem e depois das etapas de 1 a 5, conforme descrito no diagrama. As oito etapas são:
  
![Visão geral do processo de instalação.](../../media/b1a59b39-a7f0-4781-ac4d-2dfef7ca3700.png)
  
- [Instalar pré-requisitos para o Skype for Business Server](install-prerequisites.md) : Instale os pré-requisitos em todos os servidores que compõem a topologia do Skype for Business Server. Observe que os pré-requisitos não são os mesmos para todas as funções. Por exemplo, os servidores que fornecem a função de front-end têm um conjunto de pré-requisitos e os servidores que fornecem uma função de diretor têm um conjunto diferente de pré-requisitos. Consulte a documentação de planejamento de pré-requisitos para obter mais detalhes.
    
- [Criar um compartilhamento de arquivos no Skype for Business Server](create-a-file-share.md) : Crie um compartilhamento de arquivos que será usado por servidores por toda a topologia do Skype for Business Server.
    
- [Instalar ferramentas administrativas no Skype for Business Server](install-administrative-tools.md) : as ferramentas administrativas incluem o construtor de topologias e o painel de controle. Você deve instalar as ferramentas administrativas em pelo menos um servidor na topologia ou em uma estação de trabalho de gerenciamento de 64 bits executando uma versão do sistema operacional do Windows que seja compatível com o Skype for Business Server.
    
- [Preparar o Active Directory para o Skype for Business Server](prepare-active-directory.md) : o Skype for Business Server funciona em conjunto com o Active Directory. Você deve preparar o domínio do Active Directory para trabalhar com o Skype for Business Server. Você pode fazer isso por meio do assistente de implantação, e ele só é executado uma vez para o domínio. Isso ocorre porque o processo cria grupos e modifica o domínio, e você precisa fazer isso apenas uma vez.
    
- [Criar registros DNS para o Skype for Business Server](create-dns-records.md) : para que o Skype for Business Server funcione corretamente, várias configurações de DNS devem estar corretas. Isso é feito para que os clientes saibam como acessar os serviços e os servidores conhecidos. Essas configurações só precisam ser concluídas uma vez por implantação, pois depois que você atribui uma entrada DNS, ela fica disponível em todo o domínio.
    
- [Criar e publicar nova topologia no Skype for Business Server](create-and-publish-new-topology.md) : antes de poder instalar o sistema do Skype for Business Server em cada um dos servidores na topologia, você deve criar uma topologia e publicá-la. Ao publicar uma topologia, você está carregando as informações de topologia no banco de dados do repositório de gerenciamento central. Se este for um pool Enterprise Edition, você estará criando o banco de dados do repositório de gerenciamento central na primeira vez que publicar uma nova topologia. Se esta for a Standard Edition, você precisará executar o primeiro processo de preparação do servidor Standard Edition a partir do assistente de implantação antes de publicar uma topologia. Isso prepara para o Standard Edition instalando uma instância do SQL Server Express Edition e criando o repositório de gerenciamento central.
    
- [Instale o Skype for Business Server em servidores na topologia](install-skype-for-business-server.md) : depois que a topologia é carregada no repositório de gerenciamento central e o Active Directory sabe quais servidores executarão quais funções, você precisará instalar o sistema do Skype for Business Server em cada um dos servidores da topologia.
    
- [Verificar a topologia no Skype for Business Server](verify-the-topology.md) : após a topologia publicada e os componentes do sistema do Skype for Business Server instalados em cada um dos servidores na topologia, você estará pronto para verificar se a topologia está funcionando conforme o esperado. Isso inclui verificar se a configuração foi propagada para todos os servidores do Active Directory de modo que todo o domínio saiba que o Skype for Business está disponível no domínio.
    

