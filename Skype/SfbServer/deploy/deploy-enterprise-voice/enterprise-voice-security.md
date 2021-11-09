---
title: Pré-requisitos de segurança e configuração para Enterprise Voice no Skype for Business Server
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 15354abe-733e-466b-bcd4-a6cfbf58caf8
description: 'Resumo: saiba mais sobre os pré-requisitos de segurança e configuração para Enterprise Voice no Skype for Business Server.'
ms.openlocfilehash: 01f7be3bfe3e43d53d574632f228681be5af4ba4
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/08/2021
ms.locfileid: "60839073"
---
# <a name="security-and-configuration-prerequisites-for-enterprise-voice-in-skype-for-business-server"></a>Pré-requisitos de segurança e configuração para Enterprise Voice no Skype for Business Server
 
**Resumo:** Saiba mais sobre os pré-requisitos de segurança e configuração para Enterprise Voice no Skype for Business Server.
  
Antes de implantar Enterprise Voice, verifique se sua infraestrutura atende aos seguintes pré-requisitos de segurança, configuração do usuário e hardware específicos do cenário. 
  
## <a name="administrative-rights-and-certificate-infrastructure"></a>Infraestrutura de certificados e direitos administrativos

Antes de implantar, verifique o seguinte:
  
- Os administradores responsáveis pela implantação do Enterprise Voice devem ser membros do grupo RTCUniversalServerAdmins.
    
- Administradores realizando as tarefas de configuração devem ter direitos adequados:
    
  - **CsVoiceAdministrator:** Essa função de administrador pode realizar as tarefas de configuração de voz, gerenciar os aplicativos de voz e designar as políticas de voz aos usuários finais.
    
  - **CsUserAdministrator:** Essa função de administrador pode gerenciar as propriedades do usuário, como habilitar o Enterprise Voice para um usuário, pode designar políticas por usuário, com exceção da política de arquivamento, além de mover usuários e gerenciar telefones de área comum e dispositivos análogos.
    
  - **CsAdministrator:** Essa função de administrador pode realizar todas as tarefas do CsVoiceAdministrator e do CsUserAdministrator.
    
- A infraestrutura de chave gerenciada (MKI) é implantada e configurada, usando uma infraestrutura de autoridade de certificação (CA) da Microsoft ou de um terceiro.
    
    > [!NOTE]
    > Para obter detalhes sobre os requisitos de certificado Skype for Business Server, consulte [Environmental requirements for Skype for Business Server 2015](../../plan-your-deployment/requirements-for-your-environment/environmental-requirements.md) or Server requirements for Skype for Business Server [2019](../../../SfBServer2019/plan/system-requirements.md). 
  
## <a name="user-configuration"></a>Configuração do usuário

Se você colocar o Servidor de Mediação com cada pool de Front-End ou servidor Edição Standard durante a implantação do Front End, as configurações de usuário necessárias para Enterprise Voice foram configuradas automaticamente durante a instalação dos arquivos para essas funções de servidor.
  
Se você estiver recém implantando a carga de trabalho do Enterprise Voice, antes de iniciar o processo de implantação, designe um número de telefone principal para cada usuário que você planeja habilitar para o Enterprise Voice. Como administrador, você é responsável por certificar-se que esse número seja exclusivo. Antes da implementação, todos os números de telefone primários devem ser normalizados (formatados corretamente) e copiados para a propriedade **URI** de linha de cada usuário usando Skype for Business Server Painel de Controle.
  
> [!NOTE]
> Para exemplos de números de telefone primários necessários para Enterprise Voice implantação, consulte [Regras de Normalização de Exemplo.](../../plan-your-deployment/enterprise-voice-solution/outbound-voice-routing.md#BKMK_SampleNormalizationRules) 
  
## <a name="next-steps-install-files-or-configure-pstn-connectivity"></a>Próximas etapas: Instalar arquivos ou configurar a conectividade PSTN

Depois de verificar os pré-requisitos de software e ambiente para Enterprise Voice você pode:
  
- Instale o Servidor de Mediação, conforme descrito em [Deploy a Mediation Server in Topology Builder in Skype for Business Server](deploy-a-mediation-server.md), mas somente se você quiser implantar um Servidor de Mediação autônomo ou pool porque os Servidores de Mediação são instalados como parte do pool de front-end ou do processo de implantação do servidor Edição Standard quando alocados.
    
- Ou comece a configurar configurações para rotear chamadas para usuários Enterprise Voice, conforme descrito em [Configure trunks in Skype for Business Server](configure-trunks.md).
    

