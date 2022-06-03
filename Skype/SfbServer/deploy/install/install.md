---
title: Instalar o Skype for Business Server
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 7/14/2018
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection: IT_Skype16
ms.custom: Strat_SB_Admin
ms.assetid: 71299b34-8783-4384-9949-0d3162c8a36e
description: 'Resumo: saiba como preparar seu ambiente para uma instalação do Skype for Business Server.'
ms.openlocfilehash: 32003fc1c269a0bf1b59afc965099851b6406ed6
ms.sourcegitcommit: e99471689ff60f9ab1095bc075f8b4c5569c9634
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/02/2022
ms.locfileid: "65860582"
---
# <a name="install-skype-for-business-server"></a>Instalar o Skype for Business Server
 
**Resumo:** Saiba como preparar seu ambiente para uma instalação do Skype for Business Server.
  
Este artigo explica um exemplo de instalação do Skype for Business Server. Este artigo não tenta abordar todos os procedimentos necessários para executar uma instalação Skype for Business Server completa. A meta é fornecer procedimentos de exemplo em uma topologia estreitamente definida que inclui a funcionalidade básica de reunião e compartilhamento.
  
## <a name="overview-of-the-install-process-for-skype-for-business-server"></a>Visão geral do processo de instalação para Skype for Business Server

Uma instalação do Skype for Business Server inclui muitos procedimentos diferentes. Os procedimentos que você precisa para Skype for Business Server em execução em seu ambiente dependem das especificações do seu ambiente. Por exemplo, se você estiver usando o Windows Server for DNS, você se beneficiará do procedimento de exemplo para adicionar uma entrada DNS. Se você usar outro sistema para DNS, precisará seguir procedimentos para seu sistema DNS específico. Isso é verdadeiro para muitos dos procedimentos nesta seção.
  
Skype for Business Server está disponível em Edição Standard e Edição Enterprise. A principal diferença é que Edição Standard não dá suporte aos recursos de alta disponibilidade incluídos no Edição Enterprise. 
  
Skype for Business Server é um produto avançado e o processo de instalação exato depende muito de suas circunstâncias específicas. Esta seção orienta você pelas etapas gerais para instalar o produto. No entanto, cada procedimento pode ser diferente dependendo do ambiente e das decisões de planejamento. Por exemplo, para pequenas organizações, um único servidor, executar o Skype for Business Server Edição Standard pode ser apropriado, enquanto uma grande organização multinacional pode ter 50 servidores em locais em todo o mundo dedicados ao produto.
  
> [!NOTE]
> Para saber mais sobre as atualizações cumulativas mais recentes, consulte [Atualizações para Skype for Business Server](https://support.microsoft.com/kb/3061064). Depois de instalar o patch CU1, um administrador precisa executar o  `Update-CsAdminRole` cmdlet. Esse cmdlet é necessário para acessar os novos cmdlets GCP no PowerShell Remoto.
  
> [!IMPORTANT]
> Os procedimentos nesta seção servem como um exemplo usando um conjunto de requisitos definido estreitamente e pressupõem que decisões específicas já foram tomadas. Os procedimentos reais que você precisa instalar Skype for Business Server provavelmente serão muito diferentes. Use os procedimentos nesta seção apenas como exemplo e não como um guia passo a passo para instalar Skype for Business Server em todos os ambientes. 
  
Colocar Skype for Business Server em funcionamento pela primeira vez envolve oito etapas principais. Você deve entender que os procedimentos de exemplo nesta seção não são os únicos procedimentos necessários para instalar o Skype for Business Server. As oito etapas a seguir são simplesmente exemplos para ajudá-lo a entender melhor o processo geral e obter um ambiente de trabalho básico em funcionamento. Você pode executar as etapas de 1 a 5 em qualquer ordem. No entanto, você deve executar as etapas 6, 7 e 8 na ordem e após as etapas de 1 a 5, conforme descrito no diagrama. As oito etapas são:
  
![Visão geral do processo de instalação.](../../media/b1a59b39-a7f0-4781-ac4d-2dfef7ca3700.png)
  
- [Instale os pré-requisitos para Skype for Business Server](install-prerequisites.md): instale os pré-requisitos em todos os servidores que compõem a Skype for Business Server topologia. Observe que os pré-requisitos não são os mesmos para todas as funções. Por exemplo, os servidores que fornecem a função de front-end têm um conjunto de pré-requisitos e os servidores que fornecem uma função de diretor têm um conjunto diferente de pré-requisitos. Consulte a documentação de planejamento de pré-requisitos para obter mais detalhes.
    
- [Crie um compartilhamento de arquivos no Skype for Business Server](create-a-file-share.md): crie um compartilhamento de arquivos que será usado por servidores em toda a Skype for Business Server topologia.
    
- [Instalar ferramentas administrativas no Skype for Business Server](install-administrative-tools.md): as ferramentas administrativas incluem o Construtor de Topologias e Painel de Controle. Você deve instalar as ferramentas administrativas em pelo menos um servidor na topologia ou em uma estação de trabalho de gerenciamento de 64 bits executando uma versão do sistema operacional Windows compatível com Skype for Business Server.
    
- [Prepare o Active Directory para Skype for Business Server](prepare-active-directory.md): Skype for Business Server funciona em estreita proximidade com o Active Directory. Você deve preparar o domínio do Active Directory para trabalhar com Skype for Business Server. Você pode fazer isso por meio do Assistente de Implantação e isso só é feito uma vez para o domínio. Isso ocorre porque o processo cria grupos e modifica o domínio, e você precisa fazer isso apenas uma vez.
    
- [Criar registros DNS para Skype for Business Server](create-dns-records.md): para que o Skype for Business Server funcione corretamente, várias configurações de DNS devem estar em vigor. Isso é para que os clientes saibam como acessar os serviços e os servidores saibam uns sobre os outros. Essas configurações só precisam ser concluídas uma vez por implantação porque, depois de atribuir uma entrada DNS, ela estará disponível em todo o domínio.
    
- Criar e publicar nova [topologia no Skype for Business Server](create-and-publish-new-topology.md): antes de instalar o sistema Skype for Business Server em cada um dos servidores na topologia, você deve criar uma topologia e publicá-la. Ao publicar uma topologia, você está carregando as informações de topologia no banco de dados do Repositório de Gerenciamento Central. Se esse for um pool Edição Enterprise, você criará o banco de dados do Repositório de Gerenciamento Central na primeira vez que publicar uma nova topologia. Se isso for Edição Standard, você precisará executar o processo Preparar Primeiro Edição Standard Server do Assistente de Implantação antes de publicar uma topologia. Isso se prepara para Edição Standard instalando uma instância SQL Server Express Edition e criando o Repositório de Gerenciamento Central.
    
- Instale o Skype for Business Server em servidores na topologia: depois que a [topologia](install-skype-for-business-server.md) for carregada no Repositório de Gerenciamento Central e o Active Directory souber quais servidores executarão quais funções, você precisará instalar o sistema Skype for Business Server em cada um dos servidores na topologia.
    
- [Verifique a topologia no Skype for Business Server](verify-the-topology.md): depois que a topologia for publicada e os componentes do sistema do Skype for Business Server instalados em cada um dos servidores na topologia, você estará pronto para verificar se a topologia está funcionando conforme o esperado. Isso inclui verificar se a configuração foi propagada para todos os servidores do Active Directory para que todo o domínio saiba que Skype for Business está disponível no domínio.
    

