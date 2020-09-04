---
title: Planejar Sistema de Telefonia com conectividade PSTN local por meio do Skype for Business Server
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 1/26/2018
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- Ent_O365_Hybrid
- Ent_O365_Hybrid_Top
- IT_Skype16
- IT_Skype4B_Hybrid
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: 021a4c0b-d5de-4155-a506-650d758624aa
description: Saiba mais sobre as considerações de planejamento para o sistema de telefonia (Cloud PBX) com conectividade PSTN local.
ms.openlocfilehash: f8baab67191f32013a9d7a01ddc12f1b04b62c03
ms.sourcegitcommit: b424ab14683ab5080ebfd085adff7c0dbe1be84c
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/03/2020
ms.locfileid: "47358807"
---
# <a name="plan-phone-system-with-on-premises-pstn-connectivity-in-skype-for-business-server"></a>Planejar Sistema de Telefonia com conectividade PSTN local por meio do Skype for Business Server

> [!Important]
> O Skype for Business online será desativado no dia 31 de julho de 2021 depois do qual o serviço não estará mais acessível.  Além disso, a conectividade PSTN entre seu ambiente local por meio do Skype for Business Server ou do Cloud Connector Edition e do Skype for Business online não terá mais suporte.  Saiba como conectar sua rede de telefonia local ao Microsoft Teams usando o [Roteamento direto](https://docs.microsoft.com/MicrosoftTeams/direct-routing-landing-page).

Saiba mais sobre as considerações de planejamento para o sistema de telefonia (Cloud PBX) com conectividade PSTN local.

Esse conteúdo é relevante se você já tiver o Skype for Business Server ou o Lync Server 2013 implantado no local. Para outros cenários, consulte [soluções de telefonia da Microsoft](https://docs.microsoft.com/SkypeForBusiness/hybrid/msft-telephony-solutions).

 O sistema de telefonia com conectividade PSTN local permite que você aproveite os recursos do sistema de telefonia (Cloud PBX) para seus usuários. Isso pode ajudar nos seguintes cenários:

- Você tem alguns dos seus usuários do Skype for Business hospedados no local e outros hospedados no Skype for Business online. Agora você pode habilitar recursos e recursos do sistema de telefonia para seus usuários hospedados no Skype for Business Online, mas continuar a usar a conectividade PSTN local.

- Você tem uma implantação local e deseja mover alguns ou todos os seus usuários para o Skype for Business Online, mas continuar a usar a conectividade PSTN local.

    > [!IMPORTANT]
    > Para habilitar com êxito os usuários para o sistema de telefonia com conectividade PSTN local, seu endereço SIP deve estar em seu próprio domínio. Não há suporte para o uso do domínio padrão para o Microsoft 365 ou o Office 365, onmicrosoft.com. 

Para saber mais sobre o sistema de telefonia, incluindo o licenciamento e os planos, confira [planos de chamadas PSTN para o Skype for Business](https://support.office.com/article/PSTN-Calling-plans-for-Skype-for-Business-f47c6a97-bc8b-42e6-b5d4-ce6b41ed1918).

## <a name="feature-comparison"></a>Comparação de recursos

O Cloud PBX com conectividade PSTN local não oferece o mesmo conjunto de recursos que uma solução de Enterprise Voice totalmente local. Para ajudá-lo a decidir se o Cloud PBX com conectividade PSTN local fornecerá o conjunto de recursos certo para sua organização, confira [aqui o que você obtém com o Cloud PBX](https://go.microsoft.com/fwlink/?LinkId=715517).

## <a name="benefits-and-planning-considerations"></a>Benefícios e considerações de planejamento

> [!CAUTION]
> Os dispositivos do Lync Phone Edition devem ser atualizados para o firmware mínimo necessário em seu ambiente local antes de mudar para o Skype for Business online.
Se você mover seus usuários do local para o online antes de atualizar o firmware, os usuários não poderão se conectar usando seus telefones. Para corrigir esse problema, os usuários devem ser movidos de volta para o ambiente local para que seus telefones sejam atualizados para o firmware mínimo. NÃO TENTE ATUALIZAR PARA O FIRMWARE MÍNIMO OU RECONFIGURAR O TELEFONE ANTES DE TRANSFERIR O USUÁRIO DE VOLTA PARA O SEU AMBIENTE LOCAL.
Se uma reinicialização forçada for executada enquanto o dispositivo não estiver com o firmware mínimo, ele usará o padrão de autenticação de PIN, que não tem suporte no Skype for Business online. Para obter mais informações, consulte [obtendo telefones para o Skype for Business online](https://support.office.com/article/Getting-phones-for-Skype-for-Business-Online-91f2d947-45fc-4fab-bd8b-2e313531c477?ui=en-US&amp;rs=en-US&amp;ad=US).

Ao implantar o sistema de telefonia com conectividade PSTN local, você pode mover seus usuários para a nuvem via Skype for Business online em seu próprio ritmo, mantendo a conectividade PSTN local. Se você tiver um PBX, continue a usá-lo para fornecer conectividade PSTN para os usuários que você move para a nuvem. Depois que um usuário for movido para o Skype for Business Online e o sistema de telefonia, seu telefone PBX herdado não funcionará mais, mas o número de telefone encaminhará para qualquer um dos clientes do Skype for Business para computadores ou telefones inteligentes, bem como para telefones de mesa compatíveis com o Skype for Business. Uma vez portados, os usuários do sistema de telefonia e os usuários do PBX herdados podem chamar um ao outro normalmente, bem como fazer/receber chamadas PSTN usando seu número de telefone normal.

Você pode ter um recurso personalizado ou um complemento principal para seu PBX herdado, como um Call Center. Se o recurso personalizado não estiver disponível atualmente no sistema de telefonia, você deverá deixar aqueles usuários que precisam desse recurso personalizado no local com o PBX herdado e apenas portar os usuários que não precisam acessar o recurso personalizado no sistema de telefonia com conectividade PSTN local.

Para obter uma lista de PBXs herdados que interoperam diretamente com o Skype for Business Server 2015, consulte  [infraestrutura qualificada para Microsoft Lync](https://docs.microsoft.com/SkypeForBusiness/lync-cert/qualified-ip-pbx-gateway). Se seu PBX não estiver na lista, você poderá usar um controlador de borda de sessão para conectar seu PBX com o sistema de telefonia no Skype for Business online.

### <a name="network-considerations-for-quality-and-performance"></a>Considerações de rede para qualidade e desempenho

Ao implantar um serviço hospedado na nuvem como o sistema de telefonia com conectividade PSTN local, você deve ter em mente o seguinte. Em uma implantação unificada do Skype for Business Server 2015 Enterprise Voice, todos os clientes e infraestrutura estão na rede da empresa. A qualidade e o desempenho desta rede, que são fundamentais para áudio e vídeo de alta qualidade, estão sob o controle direto da equipe da empresa. Com o sistema de telefonia com conectividade PSTN local, há três redes envolvidas, duas das quais o cliente é responsável, mas apenas uma das quais a equipe corporativa tem controle direto:

- **Rede de entrega de mídia global da Microsoft** Infraestrutura e rede de nuvem global da Microsoft. Servidores e tráfego do sistema de telefonia atravessam essa rede.

- **Interconexão PSTN de empresa/nuvem** Esta é a rede que conecta sua empresa à nuvem. Isso não é necessariamente o mesmo que sua conexão genérica com a Internet.

- **Rede da sua empresa** A qualidade da mídia em tempo real é altamente dependente de sua própria rede: especialmente da rede WiFi e a qualidade da interconexão usada para chegar à nuvem.

> [!NOTE]
> Para obter mais informações sobre como ajustar o desempenho no Skype for Business Online, consulte [ajustar o desempenho do Skype for Business online](https://support.office.com/article/Tune-Skype-for-Business-Online-performance-beec23c2-c5d6-4e84-a8af-e82aefca7802?ui=en-US&amp;rs=en-US&amp;ad=US). 

## <a name="prerequisites-for-using-phone-system-with-on-premises-pstn-connectivity"></a>Pré-requisitos para usar o sistema de telefonia com conectividade PSTN local

Antes de poder configurar o sistema de telefonia com conectividade PSTN local e mover usuários para o Skype for Business Online, você deve confirmar se tem os seguintes pré-requisitos em vigor:

 **Versões do servidor local.** As versões dos servidores em sua implantação local devem estar listadas na tabela a seguir para dar suporte ao sistema de telefonia com conectividade PSTN local.


| **Função de servidor**                                       | **Versões suportadas\\**\*                                                                                         |
|:------------------------------------------------------|:-------------------------------------------------------------------------------------------------------------------|
| Borda de Federação\*\*  <br/>                            | Skype for Business Server 2015  <br/>                                                                              |
| Servidor de pool interno de rota de Federação de próximo salto  <br/> | Skype for Business Server 2015, atualização cumulativa de março de 2016 6.0.9319.235 ou superior (front-end ou diretor)  <br/> |
| Servidor de usuário front-end  <br/>                          | Skype for Business Server 2015  <br/> Lync Server 2013  <br/>                                                      |
| Servidor de Borda  <br/>                                    | Skype for Business Server 2015  <br/>                                                                              |
| Servidor de Mediação  <br/>                               | Skype for Business Server 2015  <br/> Lync Server 2013  <br/>                                                      |

\*As versões mínimas compatíveis são:

- Skype for Business Server 2015, março 2016 atualização cumulativa 6.0.9319.235

- Lync Server 2013 julho 2015 atualização cumulativa 5.0.8308.920

\*\*A rota de Federação para todos os domínios SIP com suporte deve rotear o servidor de borda do Skype for Business Server 2015 executando a atualização cumulativa de março de 2016 ou superior. Se o pool de usuários estiver no Lync Server 2013, o tráfego do pool externo permanecerá no servidor de borda do Lync Server 2013. 

Além disso, você deve garantir o seguinte:

- O **Enterprise Voice local é configurado e testado para usuários locais** Isso inclui componentes de conectividade PSTN. Para obter mais informações, consulte os seguintes tópicos se você estiver usando o Skype for Business Server 2015, consulte [Plan for Enterprise Voice in Skype for Business server 2015](../../plan-your-deployment/enterprise-voice-solution/enterprise-voice.md) e [Deploy Enterprise Voice in Skype for Business Server 2015](../../deploy/deploy-enterprise-voice/deploy-enterprise-voice.md).

    Se você estiver usando o Lync Server 2013, consulte [Planning for Enterprise Voice no Lync server 2013](https://technet.microsoft.com/library/gg413081%28v=ocs.15%29.aspx) e [implantando o Enterprise Voice no Lync Server 2013](https://technet.microsoft.com/library/gg412876%28v=ocs.15%29.aspx).

- **Sincronização do Active Directory** Você deve configurar a sincronização do Active Directory usando o Azure AD Connect. Para obter mais informações, consulte [Managing Azure ad Connect](https://azure.microsoft.com/documentation/articles/active-directory-aadconnect-whats-next/).

    > [!NOTE]
    > A versão do AAD Connect que você usa deve ser a versão 1.0.9125.0 ou posterior. Se você estiver usando uma versão anterior das ferramentas do AAD Connect ou DirSync, atualize para a versão com suporte. Você pode atualizar sua instalação atual e manter qualquer regra personalizada que tenha definido no seu ambiente. 

- **Configurar sua implantação híbrida** Se todos os seus usuários do Skype for Business estão atualmente hospedados online ou no local, ou se você tem atualmente um mix, deve concluir as etapas para configurar uma implantação híbrida do Skype for Business Server ou do Lync Server 2013, conforme descrito em [Deploy Hybrid Connectivity between Skype for Business Server e Office 365](../../skype-for-business-hybrid-solutions/deploy-hybrid-connectivity/deploy-hybrid-connectivity.md). Para obter mais informações detalhadas sobre implantações híbridas, consulte [Plan Hybrid Connectivity between Skype for Business Server e Office 365](../../skype-for-business-hybrid-solutions/plan-hybrid-connectivity.md?toc=/SkypeForBusiness/sfbhybridtoc/toc.json). 

    Se você estiver usando o Lync Server 2013, consulte [Lync server 2013 Hybrid](https://technet.microsoft.com/library/jj204805%28v=ocs.15%29.aspx).

- **Recomenda Serviços de Federação do Active Directory (AD FS).** Recomendamos implantar o AD FS para suportar o logon único. Para obter mais informações, consulte [Active Directory Federation Services (AD FS)](https://technet.microsoft.com/library/cc736690%28v=ws.10%29.aspx).

Para obter informações sobre como implantar o sistema de telefonia, consulte [habilitar usuários para o sistema de telefonia com conectividade PSTN local no Skype for Business Server](enable-users-for-phone-system.md).


