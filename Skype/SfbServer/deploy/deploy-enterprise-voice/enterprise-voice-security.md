---
title: Pré-requisitos de segurança e configuração para o Enterprise Voice no Skype para Business Server
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 15354abe-733e-466b-bcd4-a6cfbf58caf8
description: 'Resumo: Saiba mais sobre os pré-requisitos de segurança e configuração para o Enterprise Voice no Skype para Business Server.'
ms.openlocfilehash: 522252119dd6e3699dc93e0191d50a3c09c023dc
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/23/2019
ms.locfileid: "32212478"
---
# <a name="security-and-configuration-prerequisites-for-enterprise-voice-in-skype-for-business-server"></a>Pré-requisitos de segurança e configuração para o Enterprise Voice no Skype para Business Server
 
**Resumo:** Saiba mais sobre os pré-requisitos de segurança e configuração para o Enterprise Voice no Skype para Business Server.
  
Antes de implantar o Enterprise Voice, verifique se sua infraestrutura atende a seguir de segurança, configuração do usuário e os pré-requisitos de hardware específico ao cenário. 
  
## <a name="administrative-rights-and-certificate-infrastructure"></a>Direitos Administrativos e Infraestrutura do Certificado

Antes de implantar, verifique o seguinte:
  
- Os administradores a implantar o Enterprise Voice devem ser membros do grupo RTCUniversalServerAdmins.
    
- Administradores realizando as tarefas de configuração devem ter direitos adequados:
    
  - **CsVoiceAdministrator:** Essa função de administrador pode realizar as tarefas de configuração de voz, gerenciar os aplicativos de voz e designar as políticas de voz aos usuários finais.
    
  - **CsUserAdministrator:** Essa função de administrador pode gerenciar as propriedades do usuário, como habilitar o Enterprise Voice para um usuário, pode designar políticas por usuário, com exceção da política de arquivamento, além de mover usuários e gerenciar telefones de área comum e dispositivos análogos.
    
  - **CsAdministrator:** Essa função de administrador pode realizar todas as tarefas do CsVoiceAdministrator e do CsUserAdministrator.
    
- A infraestrutura de chave gerenciada (MKI) é implantada e configurada, usando uma infraestrutura de autoridade de certificação (CA) da Microsoft ou de um terceiro.
    
    > [!NOTE]
    > Para obter detalhes sobre os requisitos de certificado do Skype para Business Server, consulte [requisitos de ambiente para Skype para Business Server 2015](../../plan-your-deployment/requirements-for-your-environment/environmental-requirements.md) ou [requisitos de servidor para Skype para Business Server 2019](../../../SfBServer2019/plan/system-requirements.md). 
  
## <a name="user-configuration"></a>Configuração do usuário

Se você tiver colocado o servidor de mediação com cada pool de Front-End ou servidor Standard Edition durante a implantação de Front-End, as configurações de usuário necessárias para o Enterprise Voice foram configuradas automaticamente durante a instalação dos arquivos para essas funções de servidor.
  
Se você estiver implantando o a carga de trabalho do Enterprise Voice recentemente neste momento, antes de começar o processo de implantação, designe um número de telefone principal de cada usuário que você planeja habilitar para o Enterprise Voice. Como administrador, você é responsável por certificar-se que esse número seja exclusivo. Antes da implementação, principal de todos os números devem ser normalizados telefone (formatados corretamente) e copiado para a propriedade **URI da linha** de cada usuário usando Skype para painel de controle do Business Server.
  
> [!NOTE]
> Para obter exemplos dos números de telefone principais necessários para a implantação do Enterprise Voice, consulte [Sample Normalization Rules](../../plan-your-deployment/enterprise-voice-solution/outbound-voice-routing.md#BKMK_SampleNormalizationRules). 
  
## <a name="next-steps-install-files-or-configure-pstn-connectivity"></a>Próximas etapas: Instalar arquivos ou configurar a conectividade da PSTN

Depois de verificar os pré-requisitos de ambiente para o Enterprise Voice e software você pode:
  
- Instalar o servidor de mediação, conforme descrito em [implantar um servidor de mediação no construtor de topologia no Skype para Business Server](deploy-a-mediation-server.md), mas somente se você deseja implantar um servidor de mediação autônomo ou um pool porque os servidores de mediação são instalados como parte do Front-End pool ou no processo de implantação do Standard Edition server quando colocado.
    
- Ou então, iniciar a configuração para rotear chamadas para usuários do Enterprise Voice, conforme descrito em [Configure troncos no Skype para Business Server](configure-trunks.md).
    

