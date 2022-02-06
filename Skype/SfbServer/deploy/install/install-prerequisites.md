---
title: Instalar pré-requisitos para Skype for Business Server
ms.reviewer: null
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 2/7/2018
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
  - NOCSH
ms.localizationpriority: medium
ms.collection:
  - IT_Skype16
  - Strat_SB_Admin
ms.custom: null
ms.assetid: 2ef91a1e-2899-44c8-8e2c-527cb9114a0a
description: 'Resumo: saiba mais sobre os servidores e funções de servidor que você deve configurar antes de instalar Skype for Business Server. Baixe uma avaliação gratuita de Skype for Business Server do Centro de Avaliação da Microsoft em: https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server.'
---

# <a name="install-prerequisites-for-skype-for-business-server"></a>Instalar pré-requisitos para Skype for Business Server
 
**Resumo:** Saiba mais sobre os servidores e funções de servidor que você deve configurar antes de instalar Skype for Business Server. Baixe uma avaliação gratuita de Skype for Business Server do Centro [de Avaliação da Microsoft](https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server).
  
A instalação de pré-requisitos consiste na configuração do Windows Server instalando as funções e recursos necessários em cada um dos servidores na topologia. Os requisitos se baseiam na função que o servidor cumprirá na topologia. Você pode realizar as etapas 1 a 5 em qualquer ordem. No entanto, você deve realizar as etapas 6, 7 e 8 em ordem e após as etapas 1 a 5, conforme descrito no diagrama. Instalar pré-requisitos é a etapa 1 de 8.
  
![Diagrama de visão geral - instalar pré-requisitos.](../../media/0a85349b-b398-4e04-8901-8f4bd25d8afe.png)
  
## <a name="setup-windows-server"></a>Instalação Windows Server

Skype for Business Server requer o sistema operacional Windows Server e vários pré-requisitos antes de poder ser instalado. Para obter detalhes sobre o planejamento de pré-requisitos, consulte [Requisitos de servidor para Skype for Business Server](../../../SfBServer2019/plan/system-requirements.md). 
  
> [!TIP]
> Este procedimento usa Windows Server 2012 R2. Se você estiver usando uma versão diferente do Windows Server, o procedimento pode ser ligeiramente diferente. 
  
> [!IMPORTANT]
> Antes de começar, certifique-se de que Windows Server está atualizado usando o Windows Update. 
  
![Windows servidor atualizado.](../../media/a8d57a97-a55e-443b-b304-c534ae9a71b2.png)
  
Assista às etapas de vídeo **para instalar pré-requisitos**:
  
> [!video https://www.microsoft.com/videoplayer/embed/02447c2a-5b26-432f-aad6-b9b05cc93478?autoplay=false]
  
### <a name="install-required-roles-and-features-for-front-end-servers"></a>Instalar funções e recursos necessários para servidores front-end

Você pode instalar as funções e recursos necessários usando o Gerenciador de Servidores. 
    
1. Instale os recursos de software de pré-requisito listados nos [requisitos do servidor para Skype for Business Server](../../../SfBServer2019/plan/system-requirements.md). O software necessário deve estar no servidor que será executado Skype for Business Server.
    
    > [!CAUTION]
    > Windows Server 2012 R2 não instala todos os arquivos de origem dos recursos necessários por padrão. Se o servidor não estiver conectado à Internet, você precisará inserir a mídia Windows Server 2012 R2 e selecionar **Especificar** um caminho de origem alternativo para instalar os recursos necessários. Os arquivos de origem estão localizados no diretório sources\sxs. Por exemplo, se a mídia Windows Server 2012 R2 estiver na unidade D, você definirá o caminho como `d:\sources\sxs`. É importante que você tenha as atualizações mais recentes do Windows Update. Se você não estiver conectado à Internet, precisará instalar manualmente todas as atualizações relevantes, bem como quaisquer pré-requisitos para as atualizações necessárias. 
  
1. Quando a caixa de diálogo indicar que a instalação foi concluída, você precisará reiniciar o servidor para concluir o processo.
    
1. Execute **Windows Atualizar** novamente para verificar se há alguma atualização nas funções e serviços que foram instalados.
    
1. Se você estiver usando Skype for Business Server Painel de Controle neste servidor, você também deverá instalar o Silverlight. Para instalar o Silverlight, consulte [Microsoft Silverlight](https://www.microsoft.com/silverlight/).


> [!IMPORTANT]
> Os pré-requisitos para servidores que executam funções diferentes do servidor front-end, como a função de Diretor, Chat Persistente ou Borda, têm seus próprios pré-requisitos. Para obter detalhes sobre os pré-requisitos exatos exigidos por cada tipo de servidor, consulte [Requisitos de servidor para](../../../SfBServer2019/plan/system-requirements.md) Skype for Business Server. 
  

