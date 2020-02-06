---
title: Instalar pré-requisitos para o Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/7/2018
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 2ef91a1e-2899-44c8-8e2c-527cb9114a0a
description: 'Resumo: Saiba mais sobre as funções dos servidores e do servidor que devem ser configuradas antes de instalar o Skype for Business Server. Baixe um teste grátis do Skype for Business Server no centro de avaliação da Microsoft em https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server:.'
ms.openlocfilehash: f8ecb50525a9bb312975bf71b55a5f71c19db205
ms.sourcegitcommit: b1229ed5dc25a04e56aa02aab8ad3d4209559d8f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41791759"
---
# <a name="install-prerequisites-for-skype-for-business-server"></a>Instalar pré-requisitos para o Skype for Business Server
 
**Resumo:** Saiba mais sobre os servidores e funções de servidor que devem ser configurados antes de instalar o Skype for Business Server. Baixe um teste grátis do Skype for Business Server no [centro de avaliação da Microsoft](https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server).
  
Os pré-requisitos de instalação consistem na configuração do Windows Server por meio da instalação das funções e dos recursos necessários em cada servidor da topologia. Os requisitos são baseados na função que o servidor vai desempenhar na topologia. Você pode executar os passos 1 a 5 em qualquer ordem. No entanto, as etapas 6, 7 e 8 devem ser executadas nesta ordem, após concluir as etapas 1 a 5, conforme descrito no diagrama. Os pré-requisitos de instalação é a etapa 1 de 8.
  
![Diagrama de visão geral - instalar pré-requisitos.](../../media/0a85349b-b398-4e04-8901-8f4bd25d8afe.png)
  
## <a name="setup-windows-server"></a>Instalação do Windows Server

O Skype for Business Server exige o sistema operacional Windows Server e vários pré-requisitos antes de poder instalá-los. Para obter detalhes sobre o planejamento de pré-requisitos, consulte [requisitos do servidor para o Skype for Business Server](../../../SfBServer2019/plan/system-requirements.md). 
  
> [!TIP]
> Esse procedimento usa o Windows Server 2012 R2. Se você estiver usando uma versão diferente do Windows Server, o procedimento pode ser um pouco diferente. 
  
> [!IMPORTANT]
> Antes de começar, verifique se o Windows Server está atualizado usando o Windows Update. 
  
![O Windows Server está atualizado.](../../media/a8d57a97-a55e-443b-b304-c534ae9a71b2.png)
  
Assista as etapas do vídeo para **os pré-requisitos de instalação**:
  
> [!video https://www.microsoft.com/en-us/videoplayer/embed/02447c2a-5b26-432f-aad6-b9b05cc93478?autoplay=false]
  
### <a name="install-required-roles-and-features-for-front-end-servers"></a>Instale as funções e os recursos necessários para os servidores front-end

Você pode instalar as funções e os recursos necessários usando o Gerenciador de servidores. 
    
1. Instale os recursos de software de pré-requisito listados em [requisitos do servidor para o Skype for Business Server](../../../SfBServer2019/plan/system-requirements.md). O software necessário deve estar no servidor que executará o Skype for Business Server.
    
    > [!CAUTION]
    > O Windows Server 2012 R2 não instala todos os arquivo de origem para os recursos necessários por padrão. Se o servidor não estiver conectado à Internet, você terá que inserir a mídia do Windows Server 2012 R2 e selecionar **Especificar um caminho de origem alternativo** para instalar os recursos necessários. Os arquivos de origem estão localizados no diretório sources\sxs. Por exemplo, se a mídia do Windows Server 2012 R2 estiver na unidade D, você definiria o caminho `d:\sources\sxs`como. É importante que você tenha as atualizações mais recentes do Windows Update. Se você não estiver conectado à Internet, terá que instalar manualmente todas as atualizações importantes, bem como quaisquer pré-requisitos para as atualizações necessárias. 
  
1. Quando a caixa de diálogo indicar que a instalação foi concluída, você terá que reiniciar o servidor para concluir o processo.
    
1. Execute o **Windows Update** novamente para verificar se há alguma atualização para as funções e os serviços que foram instalados.
    
1. Se você estiver usando o painel de controle do Skype for Business Server nesse servidor, também deverá instalar o Silverlight. Para instalar o Silverlight, consulte [Microsoft Silverlight](https://www.microsoft.com/silverlight/).


> [!IMPORTANT]
> Os pré-requisitos para servidores executando funções diferentes da de servidor front-end, como a função de Diretor, Chat Persistente ou Borda, terão seus próprios pré-requisitos. Para obter detalhes sobre os pré-requisitos exatos exigidos por cada tipo de servidor, confira [requisitos de servidor para o Skype for Business Server](../../../SfBServer2019/plan/system-requirements.md). 
  

