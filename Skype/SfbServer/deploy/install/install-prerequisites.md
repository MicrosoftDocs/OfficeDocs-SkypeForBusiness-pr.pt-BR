---
title: Instalar os pré-requisitos para Skype para Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/7/2018
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 2ef91a1e-2899-44c8-8e2c-527cb9114a0a
description: 'Resumo: Saiba mais sobre os servidores e funções de servidor, que você deve configurar antes de instalar o Skype para Business Server. Baixe uma versão de avaliação gratuita do Skype para Business Server do centro da Evaluation da Microsoft em: https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server.'
ms.openlocfilehash: 6a5b6728f65d1f541687cb55811157531c70456d
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "33891807"
---
# <a name="install-prerequisites-for-skype-for-business-server"></a>Instalar os pré-requisitos para Skype para Business Server
 
**Resumo:** Saiba mais sobre os servidores e funções de servidor, que você deve configurar antes de instalar o Skype para Business Server. Baixe uma versão de avaliação gratuita do Skype para Business Server a partir do [Centro de avaliação do Microsoft](https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server).
  
Os pré-requisitos de instalação consistem na configuração do Windows Server por meio da instalação das funções e dos recursos necessários em cada servidor da topologia. Os requisitos são baseados na função que o servidor vai desempenhar na topologia. Você pode executar os passos 1 a 5 em qualquer ordem. No entanto, as etapas 6, 7 e 8 devem ser executadas nesta ordem, após concluir as etapas 1 a 5, conforme descrito no diagrama. Os pré-requisitos de instalação é a etapa 1 de 8.
  
![Diagrama de visão geral - instalar pré-requisitos.](../../media/0a85349b-b398-4e04-8901-8f4bd25d8afe.png)
  
## <a name="setup-windows-server"></a>Instalação do Windows Server

Skype para Business Server requer o sistema operacional Windows Server e um número de pré-requisitos antes que ele possa ser instalado. Para obter detalhes sobre como planejar os pré-requisitos, consulte [requisitos de servidor para Skype para Business Server](../../../SfBServer2019/plan/system-requirements.md). 
  
> [!TIP]
> Esse procedimento usa o Windows Server 2012 R2. Se você estiver usando uma versão diferente do Windows Server, o procedimento pode ser um pouco diferente. 
  
> [!IMPORTANT]
> Antes de começar, certifique-se de que o Windows Server seja atualizada usando o Windows Update. 
  
![Windows Server até a data.](../../media/a8d57a97-a55e-443b-b304-c534ae9a71b2.png)
  
Assista as etapas do vídeo para **os pré-requisitos de instalação**:
  
> [!video https://www.microsoft.com/en-us/videoplayer/embed/02447c2a-5b26-432f-aad6-b9b05cc93478?autoplay=false]
  
### <a name="install-required-roles-and-features-for-front-end-servers"></a>Instale as funções e os recursos necessários para os servidores front-end

Você pode instalar as funções e necessários recursos usando o Gerenciador de servidores. 
    
1. Instale os recursos de software de pré-requisito listados em [requisitos de servidor para Skype para Business Server](../../../SfBServer2019/plan/system-requirements.md). O software necessário deve ser no servidor que executará o Skype para Business Server.
    
    > [!CAUTION]
    > O Windows Server 2012 R2 não instala todos os arquivo de origem para os recursos necessários por padrão. Se o servidor não estiver conectado à Internet, você terá que inserir a mídia do Windows Server 2012 R2 e selecionar **Especificar um caminho de origem alternativo** para instalar os recursos necessários. Os arquivos de origem estão localizados no diretório sources\sxs. Por exemplo, se a mídia do Windows Server 2012 R2 está na unidade D, você faria definir o caminho `d:\sources\sxs`. É importante que você tenha as atualizações mais recentes do Windows Update. Se você não estiver conectado à Internet, terá que instalar manualmente todas as atualizações importantes, bem como quaisquer pré-requisitos para as atualizações necessárias. 
  
1. Quando a caixa de diálogo indicar que a instalação foi concluída, você terá que reiniciar o servidor para concluir o processo.
    
1. Execute o **Windows Update** novamente para verificar se há alguma atualização para as funções e os serviços que foram instalados.
    
1. Se você for usar Skype para painel de controle do Business Server neste servidor você também deve instalar o Silverlight. Para instalar o Silverlight, consulte [Microsoft Silverlight](https://www.microsoft.com/silverlight/).


> [!IMPORTANT]
> Os pré-requisitos para servidores executando funções diferentes da de servidor front-end, como a função de Diretor, Chat Persistente ou Borda, terão seus próprios pré-requisitos. Para obter detalhes sobre os pré-requisitos exatos exigidos por cada tipo de servidor, consulte [requisitos de servidor para Skype para Business Server](../../../SfBServer2019/plan/system-requirements.md). 
  

