---
title: Planejar o sistema telefônico no Office 365 com conectividade PSTN local no Skype Business Server
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 1/26/2018
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- Ent_O365_Hybrid
- Ent_O365_Hybrid_Top
- IT_Skype16
- IT_Skype4B_Hybrid
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: 021a4c0b-d5de-4155-a506-650d758624aa
description: Aprenda sobre as considerações de planejamento para o sistema telefônico no Office 365 (nuvem PBX) com uma conectividade PSTN local.
ms.openlocfilehash: f0e73b2541bdab8d3e37db02bc023667ae942578
ms.sourcegitcommit: d12a9f2d10093e24d4af54ce6044b512e7e3787e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/06/2019
ms.locfileid: "30454040"
---
# <a name="plan-phone-system-in-office-365-with-on-premises-pstn-connectivity-in-skype-for-business-server"></a>Planejar o sistema telefônico no Office 365 com conectividade PSTN local no Skype Business Server

Aprenda sobre as considerações de planejamento para o sistema telefônico no Office 365 (nuvem PBX) com uma conectividade PSTN local.

Esse conteúdo é relevante, se você já tiver Skype para Business Server ou o Lync Server 2013 implantados no local. Para outros cenários, consulte [soluções de telefonia da Microsoft](https://docs.microsoft.com/en-us/SkypeForBusiness/hybrid/msft-telephony-solutions).

 O sistema telefônico no Office 365 com uma conectividade PSTN local permite que você aproveite os recursos de sistema telefônico (nuvem PBX) para seus usuários. Isso pode ajudar nos seguintes cenários:

- Você tem algumas das sua Skype para negócios usuários hospedados no local e outros usuários hospedagem no Skype para negócios Online. Agora você pode habilitar o sistema telefônico nos recursos do Office 365 e recursos para os usuários hospedagem no Skype para Business Online, mas continuam a usar uma conectividade PSTN local.

- Você possui uma implantação local e você deseja mover alguns ou todos os usuários para Skype para Business Online mas continuam a usar uma conectividade PSTN local.

    > [!IMPORTANT]
    > Para habilitar os usuários com êxito para o sistema telefônico no Office 365 com conectividade PSTN de local, seu endereço SIP deve estar no seu próprio domínio. Não há suporte para o uso do domínio padrão para o Office 365 onmicrosoft.com. 

Para saber mais sobre o sistema telefônico no Office 365, incluindo planos e licenciamento, consulte [PSTN chamar planos para Skype para negócios](https://support.office.com/article/PSTN-Calling-plans-for-Skype-for-Business-f47c6a97-bc8b-42e6-b5d4-ce6b41ed1918).

## <a name="feature-comparison"></a>Comparação de recursos

PBX de nuvem com uma conectividade PSTN local não oferece o mesmo recurso definido como uma solução Enterprise Voice totalmente local. Para ajudá-lo a decidir se o PBX de nuvem com uma conectividade PSTN local fornecerá direita conjunto de recursos de sua organização, consulte [Eis os resultados obtidos com PBX de nuvem](https://go.microsoft.com/fwlink/?LinkId=715517).

## <a name="benefits-and-planning-considerations"></a>Benefícios e considerações de planejamento

> [!CAUTION]
> Os dispositivos Lync Phone Edition DEVEM ser atualizados para o firmware mínimo necessário em seu ambiente local antes de mover para o Skype for Business Online.
Se você mover seus usuários da implantação local para a online antes de atualizar o firmware, eles não conseguirão se conectar usando os seus telefones. Para corrigir esse problema, os usuários devem ser movidos de volta para o ambiente local para que seus telefones sejam atualizados para o firmware mínimo. NÃO TENTE ATUALIZAR PARA O FIRMWARE MÍNIMO OU FAZER A REINICIALIZAÇÃO FORÇADA DO TELEFONE ANTES DE MOVER O USUÁRIO DE VOLTA PARA SEU AMBIENTE LOCAL.
Se houver uma reinicialização forçada enquanto o dispositivo não estiver no firmware mínimo, o padrão será definido como Autenticação PIN, que não tem suporte no Skype for Business Online. Para obter mais informações, consulte [Getting telefones para Skype para negócios Online](https://support.office.com/en-us/article/Getting-phones-for-Skype-for-Business-Online-91f2d947-45fc-4fab-bd8b-2e313531c477?ui=en-US&amp;rs=en-US&amp;ad=US).

Implantando o sistema telefônico no Office 365 com conectividade PSTN de local, você pode mover os usuários para a nuvem via Skype para Business Online em seu próprio ritmo, enquanto mantém sua conectividade PSTN local. Se você tiver um PBX, continuará utilizando-o para fornecer conectividade PSTN aos usuários transferidos para a nuvem. Depois que um usuário é movido para Skype para Business Online e o sistema telefônico no Office 365, seu telefone PBX herdado deixarão de funcionar, mas seu número de telefone roteará para qualquer um do Skype para clientes corporativos para PCs ou Smartphones, bem como Skype para negócios compatível com telefone de mesa s. Depois de duas portas, sistema telefônico nos usuários do Office 365 e usuários herdados do PBX pode chamar umas às outras normalmente bem como fazer/receber chamadas PSTN usando o seu número de telefone normal.

Você pode ter um recurso personalizado ou um complemento de maior porte para seu PBX herdado, como um call center. Se o recurso personalizado não está disponível atualmente no sistema telefônico no Office 365, você deverá manter esses usuários que exigem esse recurso personalizado local com o PBX herdado e a porta apenas os usuários que não precisam acessar o recurso personalizado para o sistema telefônico no Office 365 com a conectividade de PSTN local.

Para obter uma lista dos PBXs herdados que interoperam diretamente com Skype para Business Server 2015 consulte [Qualificado de infra-estrutura para Microsoft Lync](https://docs.microsoft.com/SkypeForBusiness/lync-cert/qualified-ip-pbx-gateway). Se o seu PBX não estiver na lista, você pode usar um controlador de borda de sessão para conectar seu PBX com o sistema telefônico no Office 365 no Skype para negócios Online.

### <a name="network-considerations-for-quality-and-performance"></a>Considerações de rede para qualidade e desempenho

Ao implantar um serviço hospedado em nuvem, como o sistema telefônico no Office 365 com conectividade PSTN de local, você deve ter o seguinte em mente. Em um Skype puramente no local para a implantação de negócios Server 2015 Enterprise Voice, todos os clientes e infra-estrutura estão na rede da empresa. A qualidade e o desempenho dessa rede, fundamentais para que se tenha áudio e vídeo de alta qualidade, estão sob o controle direto da equipe da empresa. Com o sistema telefônico no Office 365 com conectividade PSTN de local, existem três redes envolvidas, dois dos quais o cliente é responsável por, mas apenas um da equipe da empresa tem controle direto sobre:

- **Rede de entrega de mídia Global da Microsoft** Rede global em nuvem e infraestrutura da Microsoft. Office 365 e o sistema telefônico nos servidores do Office 365 e de tráfego atravessam dessa rede.

- **Enterprise/nuvem PSTN Interconnect** Essa é a rede que se conecta a sua empresa para o Office 365 na nuvem. Isso não é necessariamente o mesmo que sua conexão genérica com a Internet.

- **Sua rede da empresa** A qualidade da mídia em tempo real é muito dependente de sua própria rede: especialmente rede WiFi e a qualidade da interconexão usada para atingir o Office 365 na nuvem.

> [!NOTE]
> Para obter mais informações sobre o ajuste de desempenho no Skype para Business Online, consulte [Skype ajuste de desempenho de negócios Online](https://support.office.com/en-us/article/Tune-Skype-for-Business-Online-performance-beec23c2-c5d6-4e84-a8af-e82aefca7802?ui=en-US&amp;rs=en-US&amp;ad=US). 

## <a name="prerequisites-for-using-phone-system-in-office-365-with-on-premises-pstn-connectivity"></a>Pré-requisitos para usar o sistema telefônico no Office 365 com conectividade PSTN de local

Antes de configurar o sistema telefônico no Office 365 com uma conectividade PSTN local e mover usuários para o Skype para Business Online, você deve confirmar que você tenha os seguintes pré-requisitos in-loco:

 **Versões do servidor local.** As versões dos servidores em sua implantação no local devem estar listadas na tabela a seguir para dar suporte a sistema telefônico no Office 365, com uma conectividade PSTN local.


| **Função de servidor**                                       | **Versões suportadas\\**\*                                                                                         |
|:------------------------------------------------------|:-------------------------------------------------------------------------------------------------------------------|
| Borda de Federação\*\*  <br/>                            | Skype for Business Server 2015  <br/>                                                                              |
| Servidor de pool interno de rota de federação de próximo salto  <br/> | Skype for Business Server 2015, atualização cumulativa 6.0.9319.235 ou posterior (tront end ou diretor) de março de 2016   <br/> |
| Servidor de usuário Front-End  <br/>                          | Skype for Business Server 2015  <br/> Lync Server 2013  <br/>                                                      |
| Servidor de Borda  <br/>                                    | Skype for Business Server 2015  <br/>                                                                              |
| Servidor de Mediação  <br/>                               | Skype for Business Server 2015  <br/> Lync Server 2013  <br/>                                                      |

\*Mínimo de versões com suporte são:

- Skype for Business Server 2015, atualização cumulativa 6.0.9319.235 de março de 2016 

- Lync Server 2013, atualização cumulativa 5.0.8308.920 de julho de 2015

\*\*A federação rotear para todos os domínios SIP com suporte devem rotear através do Skype para execução do servidor de borda do Business Server 2015 2016 ou superior de março de atualização de cumulativa. Se o pool de usuários estiver no Lync Server 2013, esse tráfego de pool externo permanecerá no Servidor de Borda do Lync Server 2013. 

Além disso você deve garantir que o seguinte:

- **Local de Enterprise Voice está configurada e testada para usuários locais** Isso inclui componentes de conectividade PSTN. Para obter mais informações, consulte os tópicos a seguir se você estiver usando o Skype para Business Server 2015, consulte [Planejar para o Enterprise Voice no Skype para Business Server 2015](../../plan-your-deployment/enterprise-voice-solution/enterprise-voice.md) e [Implantar o Enterprise Voice no Skype para Business Server 2015](../../deploy/deploy-enterprise-voice/deploy-enterprise-voice.md).

    Se você estiver usando o Lync Server 2013, consulte [Planning for Enterprise Voice no Lync Server 2013](https://technet.microsoft.com/library/gg413081%28v=ocs.15%29.aspx) e [Implantando o Enterprise Voice no Lync Server 2013](https://technet.microsoft.com/EN-US/library/gg412876%28v=ocs.15%29.aspx).

- **Sincronização do Active Directory** Você deve configurar a sincronização do Active Directory usando Connect do Azure AD. Para obter mais informações, consulte [Gerenciando o Azure AD Connect](https://azure.microsoft.com/documentation/articles/active-directory-aadconnect-whats-next/).

    > [!NOTE]
    > Você deve usar a versão 1.0.9125.0 ou posterior do AAD Connect. Se você estiver usando uma versão anterior das ferramentas do AAD Connect ou do DirSync, atualize para a versão com suporte. Você pode atualizar sua instalação atual e manter qualquer regra personalizada que você tenha definido em seu ambiente. 

- **Configure sua implantação híbrida** Se todos os seu Skype para usuários comerciais estão atualmente hospedagem tanto online ou no local, ou se você possui atualmente uma mistura, você deve concluir as etapas para configurar uma implantação híbrida do Skype para Business Server ou o Lync Server 2013, conforme descrito em [Deploy híbrida conectividade entre Skype para Business Server e Office 365](../../skype-for-business-hybrid-solutions/deploy-hybrid-connectivity/deploy-hybrid-connectivity.md). Para mais informações de plano de fundo em implantações híbridas, consulte [Planejar a conectividade híbrida entre Skype para Business Server e Office 365](../../skype-for-business-hybrid-solutions/plan-hybrid-connectivity.md?toc=/SkypeForBusiness/sfbhybridtoc/toc.json). 

    Se você estiver usando o Lync Server 2013, consulte [Lync Server 2013 hybrid](https://technet.microsoft.com/EN-US/library/jj204805%28v=ocs.15%29.aspx).

- **Serviços de Federação do Active Directory (AD FS) de (recomendado)** É recomendável implantar o AD FS para oferecer suporte a Single Sign-on. Para obter mais informações, consulte [Serviços de Federação do Active Directory (AD FS)](https://technet.microsoft.com/en-us/library/cc736690%28v=ws.10%29.aspx).

Para obter informações sobre como implantar o sistema telefônico no Office 365, consulte [habilitar usuários para o sistema telefônico no Office 365 com conectividade PSTN local no Skype para Business Server](enable-users-for-phone-system.md).


