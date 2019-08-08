---
title: Pré-requisitos de configuração e segurança do Enterprise Voice no Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 15354abe-733e-466b-bcd4-a6cfbf58caf8
description: 'Resumo: Saiba mais sobre os pré-requisitos de segurança e configuração para o Enterprise Voice no Skype for Business Server.'
ms.openlocfilehash: 70acac97bd2a3554c0613f64bdbf93f64811a0b0
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/07/2019
ms.locfileid: "36240321"
---
# <a name="security-and-configuration-prerequisites-for-enterprise-voice-in-skype-for-business-server"></a>Pré-requisitos de configuração e segurança do Enterprise Voice no Skype for Business Server
 
**Resumo:** Saiba mais sobre os pré-requisitos de segurança e configuração para o Enterprise Voice no Skype for Business Server.
  
Antes de implantar o Enterprise Voice, verifique se a sua infraestrutura atende aos seguintes pré-requisitos de segurança, configuração do usuário e hardware específico do cenário. 
  
## <a name="administrative-rights-and-certificate-infrastructure"></a>Direitos Administrativos e Infraestrutura do Certificado

Antes de implantar, verifique o seguinte:
  
- Os administradores que implantam o Enterprise Voice devem ser membros do grupo RTCUniversalServerAdmins.
    
- Administradores realizando as tarefas de configuração devem ter direitos adequados:
    
  - **CsVoiceAdministrator:** Essa função de administrador pode realizar as tarefas de configuração de voz, gerenciar os aplicativos de voz e designar as políticas de voz aos usuários finais.
    
  - **CsUserAdministrator:** Essa função de administrador pode gerenciar as propriedades do usuário, como habilitar o Enterprise Voice para um usuário, pode designar políticas por usuário, com exceção da política de arquivamento, além de mover usuários e gerenciar telefones de área comum e dispositivos análogos.
    
  - **CsAdministrator:** Essa função de administrador pode realizar todas as tarefas do CsVoiceAdministrator e do CsUserAdministrator.
    
- A infraestrutura de chave gerenciada (MKI) é implantada e configurada, usando uma infraestrutura de autoridade de certificação (CA) da Microsoft ou de um terceiro.
    
    > [!NOTE]
    > Para obter detalhes sobre os requisitos de certificado no Skype for Business Server, consulte [requisitos ambientais para requisitos de servidor do Skype for Business server 2015](../../plan-your-deployment/requirements-for-your-environment/environmental-requirements.md) ou [do Skype for Business Server 2019](../../../SfBServer2019/plan/system-requirements.md). 
  
## <a name="user-configuration"></a>Configuração do usuário

Se você colocar o servidor de mediação em cada pool de front-end ou servidor Standard Edition durante a implantação de front-end, as configurações de usuário necessárias para o Enterprise Voice foram configuradas automaticamente durante a instalação dos arquivos para essas funções de servidor.
  
Se você estiver implantando a carga de trabalho de Enterprise Voice no momento, antes de começar o processo de implantação, designe um número de telefone principal para cada usuário que você planeja habilitar para o Enterprise Voice. Como administrador, você é responsável por certificar-se que esse número seja exclusivo. Antes da implementação, todos os números de telefone primários devem ser normalizados (formatados corretamente) e copiados para cada propriedade de **URI de linha** do usuário usando o painel de controle do Skype for Business Server.
  
> [!NOTE]
> Para obter exemplos dos números de telefone principais necessários para a implantação do Enterprise Voice, consulte [Sample Normalization Rules](../../plan-your-deployment/enterprise-voice-solution/outbound-voice-routing.md#BKMK_SampleNormalizationRules). 
  
## <a name="next-steps-install-files-or-configure-pstn-connectivity"></a>Próximas etapas: Instalar arquivos ou configurar a conectividade da PSTN

Depois de verificar o software e os pré-requisitos ambientais do Enterprise Voice, você pode:
  
- Instale o servidor de mediação, conforme descrito em [implantar um servidor de mediação no construtor de topologias no servidor do Skype for Business](deploy-a-mediation-server.md), mas somente se você quiser implantar um servidor de mediação autônomo ou um pool porque os servidores de mediação são instalados como parte do front-end grupo ou o processo de implantação do servidor Standard Edition quando posicionado.
    
- Ou comece a definir as configurações para direcionar as chamadas para usuários do Enterprise Voice, conforme descrito em [Configurar troncos no Skype for Business Server](configure-trunks.md).
    

