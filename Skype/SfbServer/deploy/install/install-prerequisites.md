---
title: Instalar pré-requisitos para o Skype for Business Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
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
description: 'Resumo: saiba mais sobre os servidores e as funções de servidor que você deve configurar antes de instalar o Skype for Business Server. Baixe uma avaliação gratuita do Skype for Business Server no Centro de Avaliação da Microsoft em: https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server .'
ms.openlocfilehash: 197f2482bd6c53f3cf9814dbf6f36bb6c4bdb331
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49801711"
---
# <a name="install-prerequisites-for-skype-for-business-server"></a>Instalar pré-requisitos para o Skype for Business Server
 
**Resumo:** Saiba mais sobre os servidores e as funções de servidor que você deve configurar antes de instalar o Skype for Business Server. Baixe uma avaliação gratuita do Skype for Business Server no Centro [de Avaliação da Microsoft.](https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server)
  
A instalação dos pré-requisitos consiste em configurar o Windows Server instalando as funções e os recursos necessários em cada um dos servidores na topologia. Os requisitos são baseados na função que o servidor cumprirá na topologia. Você pode realizar as etapas 1 a 5 em qualquer ordem. No entanto, você deve realizar as etapas 6, 7 e 8 na ordem e após as etapas de 1 a 5, conforme descrito no diagrama. A instalação dos pré-requisitos é a etapa 1 de 8.
  
![Diagrama de visão geral - pré-requisitos de instalação.](../../media/0a85349b-b398-4e04-8901-8f4bd25d8afe.png)
  
## <a name="setup-windows-server"></a>Configurar o Windows Server

O Skype for Business Server requer o sistema operacional Windows Server e vários pré-requisitos para que ele possa ser instalado. Para obter detalhes sobre o planejamento de pré-requisitos, consulte [Requisitos de servidor para o Skype for Business Server.](../../../SfBServer2019/plan/system-requirements.md) 
  
> [!TIP]
> Este procedimento usa o Windows Server 2012 R2. Se você estiver usando uma versão diferente do Windows Server, o procedimento pode ser ligeiramente diferente. 
  
> [!IMPORTANT]
> Antes de começar, certifique-se de que o Windows Server está atualizado usando o Windows Update. 
  
![Windows Server atualizado.](../../media/a8d57a97-a55e-443b-b304-c534ae9a71b2.png)
  
Assista às etapas de vídeo **para instalar os pré-requisitos:**
  
> [!video https://www.microsoft.com/videoplayer/embed/02447c2a-5b26-432f-aad6-b9b05cc93478?autoplay=false]
  
### <a name="install-required-roles-and-features-for-front-end-servers"></a>Instalar funções e recursos necessários para servidores front-end

Você pode instalar as funções e os recursos necessários usando o Gerenciador do Servidor. 
    
1. Instale os recursos de software de pré-requisito listados nos [requisitos de servidor para o Skype for Business Server.](../../../SfBServer2019/plan/system-requirements.md) O software necessário deve estar no servidor que executará o Skype for Business Server.
    
    > [!CAUTION]
    > O Windows Server 2012 R2 não instala todos os arquivos de origem dos recursos necessários por padrão. Se o servidor não estiver conectado à Internet, será necessário inserir a mídia do  Windows Server 2012 R2 e selecionar Especificar um caminho de origem alternativo para instalar os recursos necessários. Os arquivos de origem estão localizados no diretório sources\sxs. Por exemplo, se a mídia do Windows Server 2012 R2 estiver na unidade D, você deve definir o caminho para `d:\sources\sxs` . É importante que você tenha as atualizações mais recentes do Windows Update. Se você não estiver conectado à Internet, será necessário instalar manualmente todas as atualizações relevantes, bem como quaisquer pré-requisitos para as atualizações necessárias. 
  
1. Quando a caixa de diálogo indicar que a instalação foi concluída, será necessário reiniciar o servidor para concluir o processo.
    
1. Execute **o Windows Update** novamente para verificar se há alguma atualização para as funções e serviços que foram instalados.
    
1. Se você for usar o Painel de Controle do Skype for Business Server neste servidor, também deverá instalar o Silverlight. Para instalar o Silverlight, consulte [o Microsoft Silverlight.](https://www.microsoft.com/silverlight/)


> [!IMPORTANT]
> Os pré-requisitos para servidores que executam funções diferentes do servidor front-end, como a função de Diretor, Chat Persistente ou Borda, têm seus próprios pré-requisitos. Para obter detalhes sobre os pré-requisitos exatos exigidos por cada tipo de servidor, consulte Requisitos de [servidor para o Skype for Business Server.](../../../SfBServer2019/plan/system-requirements.md) 
  

