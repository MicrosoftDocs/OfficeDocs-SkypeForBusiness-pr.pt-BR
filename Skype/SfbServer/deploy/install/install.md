---
title: Instalar o Skype for Business Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
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
description: 'Resumo: Saiba como preparar seu ambiente para uma instalação do Skype for Business Server. Baixe uma avaliação gratuita do Skype for Business Server no Centro de Avaliação da Microsoft em: https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server .'
ms.openlocfilehash: ef562a56e1129481954f9345a46483156bd1202f
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49801911"
---
# <a name="install-skype-for-business-server"></a>Instalar o Skype for Business Server
 
**Resumo:** Saiba como preparar seu ambiente para uma instalação do Skype for Business Server. Baixe uma avaliação gratuita do Skype for Business Server no Centro de Avaliação da Microsoft em: [https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server](https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server) .
  
Este artigo apresenta um exemplo de instalação do Skype for Business Server. Este artigo não tenta abranger todos os procedimentos necessários para executar uma instalação completa do Skype for Business Server. O objetivo é fornecer procedimentos de exemplo em uma topologia estreitamente definida que inclui a funcionalidade básica de reunir e compartilhar.
  
## <a name="overview-of-the-install-process-for-skype-for-business-server"></a>Visão geral do processo de instalação do Skype for Business Server

Uma instalação do Skype for Business Server inclui vários procedimentos diferentes. Os procedimentos necessários para que o Skype for Business Server seja executado em seu ambiente dependem das especificidades do seu ambiente. Por exemplo, se você estiver usando o Windows Server para DNS, se beneficiará do procedimento de exemplo para adicionar uma entrada DNS. Se você usar outro sistema para DNS, precisará seguir os procedimentos para seu sistema DNS específico. Isso é verdadeiro para muitos dos procedimentos nesta seção.
  
O Skype for Business Server está disponível em Standard Edition e Enterprise Edition. A principal diferença é que o Standard Edition não dá suporte aos recursos de alta disponibilidade incluídos no Enterprise Edition. 
  
O Skype for Business Server é um produto avançado, e o processo de instalação exato depende muito de suas circunstâncias específicas. Esta seção orienta você pelas etapas gerais para instalar o produto. No entanto, cada procedimento pode ser diferente dependendo do ambiente e das decisões de planejamento. Por exemplo, para pequenas organizações, um único servidor, executar o Skype for Business Server Standard Edition pode ser apropriado, enquanto uma grande organização multinacional pode ter 50 servidores em locais em todo o mundo dedicados ao produto.
  
> [!NOTE]
> Para saber mais sobre as atualizações cumulativas mais recentes, consulte [Atualizações do Skype for Business Server.](https://support.microsoft.com/kb/3061064) Depois de instalar o patch CU1, um administrador precisa executar  `Update-CsAdminRole` o cmdlet. Este cmdlet é necessário para acessar os novos cmdlets GCP sobre o PowerShell Remoto.
  
> [!IMPORTANT]
> Os procedimentos nesta seção servem como exemplo usando um conjunto de requisitos definido por restrições e assumindo que decisões específicas já foram tomadas. Os procedimentos reais que você precisa para instalar o Skype for Business Server provavelmente serão muito diferentes. Use os procedimentos nesta seção como um exemplo apenas e não como um guia passo a passo para instalar o Skype for Business Server em todos os ambientes. 
  
A execução do Skype for Business Server pela primeira vez envolve oito etapas principais. Você deve entender que os procedimentos de exemplo nesta seção não são os únicos procedimentos necessários para instalar o Skype for Business Server. As oito etapas a seguir são simplesmente exemplos para ajudá-lo a entender melhor o processo geral e obter um ambiente de trabalho básico em funcionamento. Você pode realizar as etapas 1 a 5 em qualquer ordem. No entanto, você deve realizar as etapas 6, 7 e 8 na ordem e após as etapas de 1 a 5, conforme descrito no diagrama. As oito etapas são:
  
![Visão geral do processo de instalação.](../../media/b1a59b39-a7f0-4781-ac4d-2dfef7ca3700.png)
  
- [Instalar pré-requisitos para o Skype for Business Server:](install-prerequisites.md) instalar pré-requisitos em todos os servidores que compom a topologia do Skype for Business Server. Observe que os pré-requisitos não são os mesmos para todas as funções. Por exemplo, os servidores que fornecem a função front-end têm um conjunto de pré-requisitos, e os servidores que fornecem uma função de diretor têm um conjunto diferente de pré-requisitos. Consulte a documentação de planejamento de pré-requisitos para obter mais detalhes.
    
- [Crie um compartilhamento de arquivos no Skype for Business Server:](create-a-file-share.md) crie um compartilhamento de arquivos que será usado pelos servidores em toda a topologia do Skype for Business Server.
    
- [Instalar ferramentas administrativas no Skype for Business Server:](install-administrative-tools.md) as ferramentas administrativas incluem o Construtor de Topologias e o Painel de Controle. Você deve instalar as ferramentas administrativas em pelo menos um servidor na topologia ou em uma estação de trabalho de gerenciamento de 64 bits executando uma versão do sistema operacional Windows com suporte para o Skype for Business Server.
    
- [Preparar o Active Directory para o Skype for Business Server:](prepare-active-directory.md) o Skype for Business Server funciona em estreita proximidade com o Active Directory. Você deve preparar o domínio do Active Directory para trabalhar com o Skype for Business Server. Você pode fazer isso por meio do Assistente de Implantação, e isso só é feito uma vez para o domínio. Isso porque o processo cria grupos e modifica o domínio, e você precisa fazer isso apenas uma vez.
    
- [Criar registros DNS para o Skype for Business Server:](create-dns-records.md) para que o Skype for Business Server funcione corretamente, várias configurações de DNS devem estar em funcionamento. Isso é para que os clientes saibam como acessar os serviços e os servidores saibam uns sobre os outros. Essas configurações só precisam ser concluídas uma vez por implantação porque, depois de atribuir uma entrada DNS, ela estará disponível em todo o domínio.
    
- Crie e publique nova topologia no [Skype for Business Server:](create-and-publish-new-topology.md) antes de instalar o sistema Skype for Business Server em cada um dos servidores na topologia, você deve criar uma topologia e publicá-la. Ao publicar uma topologia, você está carregando as informações de topologia no banco de dados do Armazenamento de Gerenciamento Central. Se for um pool Enterprise Edition, você criará o banco de dados do Armazenamento de Gerenciamento Central na primeira vez que publicar uma nova topologia. Se for o Standard Edition, você precisará executar o processo Preparar Primeiro Servidor Standard Edition do Assistente de Implantação antes de publicar uma topologia. Isso se prepara para o Standard Edition instalando uma instância do SQL Server Express Edition e criando o Armazenamento de Gerenciamento Central.
    
- Instale o Skype for Business Server em servidores na topologia: depois que a [topologia](install-skype-for-business-server.md) for carregada no Armazenamento de Gerenciamento Central e o Active Directory souber quais servidores executarão quais funções, será necessário instalar o sistema skype for Business Server em cada um dos servidores na topologia.
    
- Verifique a topologia no [Skype for Business Server:](verify-the-topology.md) depois de publicar a topologia e instalar os componentes do sistema do Skype for Business Server em cada um dos servidores na topologia, você estará pronto para verificar se a topologia está funcionando conforme o esperado. Isso inclui verificar se a configuração foi propagada para todos os servidores do Active Directory para que o domínio inteiro saiba que o Skype for Business está disponível no domínio.
    

