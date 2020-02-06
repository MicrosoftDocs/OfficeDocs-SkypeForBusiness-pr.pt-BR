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
description: 'Resumo: saiba como preparar seu ambiente para uma instalação do Skype for Business Server. Baixe um teste grátis do Skype for Business Server no centro de avaliação da Microsoft em https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server:.'
ms.openlocfilehash: cac618aba9f97237e585ffc57b99c71a8a5c8645
ms.sourcegitcommit: b1229ed5dc25a04e56aa02aab8ad3d4209559d8f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41797082"
---
# <a name="install-skype-for-business-server"></a>Instalar o Skype for Business Server
 
**Resumo:** Saiba como preparar seu ambiente para uma instalação do Skype for Business Server. Baixe um teste grátis do Skype for Business Server no centro de avaliação da Microsoft em[https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server](https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server):.
  
Este artigo orienta você por meio de uma instalação de exemplo do Skype for Business Server. Este artigo não tenta abranger todos os procedimentos que você precisa para executar uma instalação completa do Skype for Business Server. O objetivo é dar exemplos de procedimentos em uma topologia definida de forma limitada que inclua a funcionalidade básica de reunir e compartilhar.
  
## <a name="overview-of-the-install-process-for-skype-for-business-server"></a>Visão geral do processo de instalação do Skype for Business Server

Uma instalação do Skype for Business Server inclui muitos procedimentos diferentes. Os procedimentos que você precisa para obter o Skype for Business Server em execução em seu ambiente dependem dos específicos do seu ambiente. Por exemplo, se você estiver usando o Windows Server para DNS, aproveite o exemplo do procedimento sobre como adicionar uma entrada DNS. Caso você use outro sistema de DNS, será necessário seguir os procedimentos referentes ao seu sistema de DNS. Isto se aplica a vários procedimentos desta seção.
  
O Skype for Business Server está disponível no Standard Edition e no Enterprise Edition. A diferença principal é que a versão Standard Edition não suporta os recursos de alta disponibilidade incluídos na versão Enterprise Edition. 
  
O Skype for Business Server é um produto avançado, e o processo de instalação exato depende de um ótimo negócio em circunstâncias específicas. Esta seção ilustra as etapas gerais necessárias para instalar o produto. No entanto, cada procedimento pode ser diferente, dependendo do seu ambiente e das decisões de planejamento. Por exemplo, para pequenas organizações, um único servidor que executa o Skype for Business Server Standard Edition pode ser adequado, enquanto uma grande organização multinacional pode ter 50 servidores em locais em todo o mundo dedicado ao produto.
  
> [!NOTE]
> Para saber mais sobre as atualizações cumulativas mais recentes, confira [atualizações para o Skype for Business Server](https://support.microsoft.com/en-us/kb/3061064). Depois de instalar o patch CU1, um administrador precisa executar `Update-CsAdminRole` o cmdlet. Este cmdlet é necessário para acessar os novos cmdlets GCP sobre o PowerShell Remoto.
  
> [!IMPORTANT]
> Os procedimentos nesta seção têm como finalidade servir de exemplo, usando um conjunto limitado de requisitos e assumindo que decisões específicas já foram tomadas. Os procedimentos reais necessários para instalar o Skype for Business Server provavelmente serão muito diferentes. Use os procedimentos desta seção como exemplo apenas e não como um guia passo a passo para instalar o Skype for Business Server em todos os ambientes. 
  
Colocar o Skype for Business Server em funcionamento pela primeira vez envolve oito etapas principais. Você deve entender que os procedimentos de exemplo desta seção não são os únicos procedimentos necessários para a instalação do Skype for Business Server. As oito etapas a seguir são simplesmente exemplos para ajudá-lo a entender melhor o processo geral e obter um ambiente de trabalho básico em funcionamento. Você pode executar os passos 1 a 5 em qualquer ordem. Entretanto, deve executar as etapas 6, 7 e 8 na ordem certa, e após as etapas de 1 a 5, conforme descrito no diagrama. As oito etapas são:
  
![Visão geral do processo de instalação.](../../media/b1a59b39-a7f0-4781-ac4d-2dfef7ca3700.png)
  
- [Instalar pré-requisitos para o Skype for Business Server](install-prerequisites.md) : Instale pré-requisitos em todos os servidores que compõem a topologia do Skype for Business Server. Observe que os pré-requisitos não são os mesmos para todas as funções. Por exemplo, servidores que fornecem uma função de front-end têm um conjunto de pré-requisitos, enquanto servidores que fornecem uma função de diretor têm outro conjunto de pré-requisitos completamente diferente. Consulte a documentação sobre planejamento de pré-requisitos para obter mais detalhes.
    
- [Crie um compartilhamento de arquivos no Skype for Business Server](create-a-file-share.md) : Crie um compartilhamento de arquivos que será usado por servidores em toda a topologia do Skype for Business Server.
    
- [Instale as ferramentas administrativas no Skype for Business Server](install-administrative-tools.md) : as ferramentas administrativas incluem o construtor de topologias e o painel de controle. Você deve instalar as ferramentas administrativas em pelo menos um servidor na topologia ou em uma estação de trabalho de gerenciamento de 64 executando uma versão do sistema operacional do Windows que seja compatível com o Skype for Business Server.
    
- [Preparar o Active Directory para o Skype for Business Server](prepare-active-directory.md) : o Skype for Business Server funciona em conjunto com o Active Directory. Você deve preparar o domínio do Active Directory para funcionar com o Skype for Business Server. Você pode fazer isso por meio do Assistente de Implantação, e isso só é feito uma única vez para o domínio. Como esse processo cria grupos e modifica o domínio, você só precisa fazer isso uma vez.
    
- [Criar registros de DNS para o Skype for Business Server](create-dns-records.md) : para que o Skype for Business Server funcione corretamente, várias configurações de DNS devem estar corretas. Deve ser feito de forma que os clientes saibam como acessar os serviços e os servidores se identifiquem entre si. Essas configurações só precisam ser concluídas uma vez por implantação já que a entrada DNS fica disponível por todo o domínio depois de ser atribuída.
    
- [Criar e publicar nova topologia no Skype for Business Server](create-and-publish-new-topology.md) : antes de poder instalar o sistema do Skype for Business Server em cada um dos servidores na topologia, você deve criar uma topologia e publicá-la. Ao publicar uma topologia, você está carregando as informações da topologia no banco de dados do Repositório de Gerenciamento Central. Se este for um pool Enterprise Edition, você estará criando um banco de dados do Repositório de Gerenciamento Central na primeira vez em que publicar uma topologia nova. Já se for a Standard Edition, será necessário executar o processo Preparar primeiro servidor Standard Edition no Assistente de Implantação antes de publicar um topologia. É a preparação da versão Standard Edition com a instalação de uma instância do SQL Server Express Edition e a criação de um Repositório de Gerenciamento Central.
    
- [Instale o Skype for Business Server em servidores na topologia](install-skype-for-business-server.md) : depois que a topologia é carregada no repositório de gerenciamento central e o Active Directory sabe quais servidores executarão quais funções, você precisará instalar o sistema do Skype for Business Server em cada um dos servidores da topologia.
    
- [Verifique a topologia no Skype for Business Server](verify-the-topology.md) : após a publicação da topologia e dos componentes do sistema do Skype for Business Server instalados em cada um dos servidores na topologia, você estará pronto para verificar se a topologia está funcionando conforme o esperado. Isso inclui verificar se a configuração foi propagada para todos os servidores do Active Directory para que todo o domínio saiba que o Skype for Business está disponível no domínio.
    

