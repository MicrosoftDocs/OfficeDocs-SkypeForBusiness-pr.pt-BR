---
title: Instalar o Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 7/14/2018
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.custom: Strat_SB_Admin
ms.assetid: 71299b34-8783-4384-9949-0d3162c8a36e
description: 'Resumo: Saiba como preparar seu ambiente para uma instalação do Skype para Business Server. Baixe uma versão de avaliação gratuita do Skype para Business Server do centro da Evaluation da Microsoft em: https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server.'
ms.openlocfilehash: ab3b66b99ff1c144631622dfd59a7326e516154b
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "33894327"
---
# <a name="install-skype-for-business-server"></a>Instalar o Skype for Business Server
 
**Resumo:** Saiba como preparar seu ambiente para uma instalação do Skype para Business Server. Baixe uma versão de avaliação gratuita do Skype para Business Server do centro da Evaluation da Microsoft em:[https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server](https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server).
  
Este artigo o orienta durante uma instalação de exemplo do Skype para Business Server. Este artigo não tentará cobrir todos os procedimentos que você precisa realizar um Skype completo para instalação do servidor de negócios. O objetivo é dar exemplos de procedimentos em uma topologia definida de forma limitada que inclua a funcionalidade básica de reunir e compartilhar.
  
## <a name="overview-of-the-install-process-for-skype-for-business-server"></a>Visão geral do processo de instalação de Skype para Business Server

Uma instalação do Skype para Business Server inclui muitos procedimentos diferentes. Os procedimentos que você precisa obter Skype Business Server em execução no seu ambiente dependem as especificações de seu ambiente. Por exemplo, se você estiver usando o Windows Server para DNS, aproveite o exemplo do procedimento sobre como adicionar uma entrada DNS. Caso você use outro sistema de DNS, será necessário seguir os procedimentos referentes ao seu sistema de DNS. Isto se aplica a vários procedimentos desta seção.
  
Skype para Business Server está disponível no Standard Edition e Enterprise Edition. A diferença principal é que a versão Standard Edition não suporta os recursos de alta disponibilidade incluídos na versão Enterprise Edition. 
  
Skype para Business Server é um produto avançado e o processo de instalação exato depende muito circunstâncias específicas. Esta seção ilustra as etapas gerais necessárias para instalar o produto. No entanto, cada procedimento pode ser diferente, dependendo do seu ambiente e das decisões de planejamento. Por exemplo, para pequenas organizações um único servidor, executando o Skype para Business Server Standard Edition pode ser apropriado, enquanto uma grande organização multinacional pode ter 50 servidores nos locais em todo o mundo dedicada ao produto.
  
> [!NOTE]
> Para saber mais sobre as últimas atualizações cumulativas, consulte [Updates for Skype para Business Server](https://support.microsoft.com/en-us/kb/3061064). Depois de instalar o patch CU1, um administrador precisa executar o `Update-CsAdminRole` cmdlet. Este cmdlet é necessário para acessar os novos cmdlets GCP sobre o PowerShell Remoto.
  
> [!IMPORTANT]
> Os procedimentos nesta seção têm como finalidade servir de exemplo, usando um conjunto limitado de requisitos e assumindo que decisões específicas já foram tomadas. Os procedimentos reais, que você precisará instalar Skype para Business Server provavelmente será muito diferentes. Use os procedimentos nesta seção como um exemplo apenas e não como um guia passo a passo para instalar o Skype para Business Server em cada ambiente. 
  
Aprendendo Skype para Business Server e executando-se pela primeira vez envolvem oito etapas principais. Você deve compreender os procedimentos de exemplo nesta seção não estão os somente procedimentos necessários para instalar o Skype for Business Server. As seguintes oito etapas são simplesmente exemplos para ajudá-lo compreendam o processo geral e obtém uma trabalhando o ambiente de e a execução. Você pode executar os passos 1 a 5 em qualquer ordem. Entretanto, deve executar as etapas 6, 7 e 8 na ordem certa, e após as etapas de 1 a 5, conforme descrito no diagrama. As oito etapas são:
  
![Visão geral do processo de instalação.](../../media/b1a59b39-a7f0-4781-ac4d-2dfef7ca3700.png)
  
- [Instalar os pré-requisitos do Skype para Business Server](install-prerequisites.md) : instalar pré-requisitos em todos os servidores que compõem o Skype para a topologia de servidor de negócios. Observe que os pré-requisitos não são os mesmos para todas as funções. Por exemplo, servidores que fornecem uma função de front-end têm um conjunto de pré-requisitos, enquanto servidores que fornecem uma função de diretor têm outro conjunto de pré-requisitos completamente diferente. Consulte a documentação sobre planejamento de pré-requisitos para obter mais detalhes.
    
- [Criar um compartilhamento de arquivo no Skype para Business Server](create-a-file-share.md) : criar um compartilhamento de arquivo que será usado pelos servidores em todo o Skype para a topologia de servidor de negócios.
    
- [Instalar as ferramentas administrativas em Skype para Business Server](install-administrative-tools.md) : as ferramentas administrativas incluem o construtor de topologia e em Painel de controle. Você deve instalar as ferramentas administrativas em pelo menos um servidor da topologia ou uma estação de trabalho de gerenciamento de 64 bits executando uma versão do sistema operacional Windows que é suportada para Skype para Business Server.
    
- [Preparar o Active Directory para Skype para Business Server](prepare-active-directory.md) : Skype para Business Server trabalha em conjunto com o Active Directory. Você deve preparar o domínio do Active Directory para funcionar com Skype para Business Server. Você pode fazer isso por meio do Assistente de Implantação, e isso só é feito uma única vez para o domínio. Como esse processo cria grupos e modifica o domínio, você só precisa fazer isso uma vez.
    
- [Criar registros DNS para Skype para Business Server](create-dns-records.md) : na ordem para Skype Business Server funcionem adequadamente, várias configurações de DNS devem estar no lugar. Deve ser feito de forma que os clientes saibam como acessar os serviços e os servidores se identifiquem entre si. Essas configurações só precisam ser concluídas uma vez por implantação já que a entrada DNS fica disponível por todo o domínio depois de ser atribuída.
    
- [Criar e publicar a nova topologia no Skype para Business Server](create-and-publish-new-topology.md) : antes de instalar o Skype para system Business Server em cada um dos servidores na topologia, você deve criar uma topologia e publicá-lo. Ao publicar uma topologia, você está carregando as informações da topologia no banco de dados do Repositório de Gerenciamento Central. Se este for um pool Enterprise Edition, você estará criando um banco de dados do Repositório de Gerenciamento Central na primeira vez em que publicar uma topologia nova. Já se for a Standard Edition, será necessário executar o processo Preparar primeiro servidor Standard Edition no Assistente de Implantação antes de publicar um topologia. É a preparação da versão Standard Edition com a instalação de uma instância do SQL Server Express Edition e a criação de um Repositório de Gerenciamento Central.
    
- [Instale o Skype para Business Server nos servidores na topologia](install-skype-for-business-server.md) : depois que a topologia é carregada no repositório de gerenciamento Central e o Active Directory sabe quais servidores executarão quais funções, você precisará instalar o Skype para system Business Server em cada um dos os servidores na topologia.
    
- [Verificar a topologia no Skype para Business Server](verify-the-topology.md) : depois que a topologia publicada e o Skype para componentes do sistema Business Server instalado em cada um dos servidores na topologia, você estará pronto para verificar se a topologia está funcionando conforme o esperado. Isso inclui a verificação de que a configuração tenha propagadas check-out para todos os servidores do Active Directory para que o domínio inteiro reconheça Skype para a empresa está disponível no domínio.
    

