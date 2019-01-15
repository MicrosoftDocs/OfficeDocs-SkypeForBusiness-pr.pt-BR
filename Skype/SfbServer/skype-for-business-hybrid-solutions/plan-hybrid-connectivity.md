---
title: Planejar a conectividade híbrida entre o Skype for Business Server e o Skype for Business Online
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 1/23/2018
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
ms.assetid: f8b3d240-bc2e-42c9-acf8-d532d641a14c
description: 'Resumo: Leia este tópico para saber como planejar a conectividade híbrida entre o Skype for Business Server e o Skype for Business Online.  A configuração da conectividade híbrida é a primeira etapa da implantação de muitas soluções híbridas do Skype for Business.'
ms.openlocfilehash: 8fd32e8b70f2fc63919b9ec8abca2d0b70c90107
ms.sourcegitcommit: 155029842e76cc7ae08da48c55ba7ec827d0505c
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/15/2019
ms.locfileid: "28015282"
---
# <a name="plan-hybrid-connectivity-between-skype-for-business-server-and-skype-for-business-online"></a>Planejar a conectividade híbrida entre o Skype for Business Server e o Skype for Business Online

**Resumo:** Leia este tópico para saber como planejar a conectividade híbrida entre o Skype for Business Server e o Skype for Business Online.  A configuração da conectividade híbrida é a primeira etapa da implantação de muitas soluções híbridas do Skype for Business.

Este tópico fornece uma visão geral e descreve a infraestrutura e requisitos de sistema, você precisará configurar a conectividade híbrida entre as existentes no local Skype para implantação de servidor de negócios — com usuários que foram criados no seu local Active Directory — e Skype para negócios on-line.

Este tópico inclui as seguintes seções:

- [Overview](plan-hybrid-connectivity.md#BKMK_Overview)

- [Requisitos de infraestrutura](plan-hybrid-connectivity.md#BKMK_Infrastructure)

- [Suporte a várias florestas](plan-hybrid-connectivity.md#BKMK_MultiForest)

- [Coexistência do Exchange](plan-hybrid-connectivity.md#BKMK_Exchange)

- [Credenciais do administrador](plan-hybrid-connectivity.md#BKMK_Credentials)

- [PowerShell do Skype for Business Online](plan-hybrid-connectivity.md#BKMK_PowerShell)

- [Suporte ao cliente do Skype for Business](plan-hybrid-connectivity.md#BKMK_ClientSupport)

- [Requisitos de topologia](plan-hybrid-connectivity.md#BKMK_Topology)

- [Requisitos das listas de permissões/bloqueios da federação](plan-hybrid-connectivity.md#BKMK_Federation)

- [Configurações de DNS](plan-hybrid-connectivity.md#BKMK_DNS)

- [Considerações sobre o firewall](plan-hybrid-connectivity.md#BKMK_Firewall)

- [Requisitos de porta e protocolo](plan-hybrid-connectivity.md#BKMK_Ports)

- [Dados e contas de usuário](plan-hybrid-connectivity.md#BKMK_UserAccounts)

- [Recursos e políticas de usuário](plan-hybrid-connectivity.md#BKMK_UserPolicies)

Depois de ler este tópico, quando estiver pronto para a implantação, veja [Deploy hybrid connectivity between Skype for Business Server and Skype for Business Online](deploy-hybrid-connectivity/deploy-hybrid-connectivity.md). Os tópicos sobre a implantação fornecem orientações passo a passo para configurar a conectividade híbrida entre sua implantação local e o Skype for Business Online.

(Para obter informações sobre como configurar o Lync Server 2013 ou a implantação do Lync Server 2010 para o híbrido, consulte [Lync Server 2013 hybrid](https://go.microsoft.com/fwlink/p/?LinkId=617360).)

## <a name="overview"></a>Visão geral
<a name="BKMK_Overview"> </a>

As soluções híbridas permitem que você migre seus usuários para a nuvem de acordo com seu cronograma e suas necessidades comerciais. Este tópico foca a conectividade híbrida entre uma implantação local do Skype for Business Server e do Skype for Business Online. Essa conectividade permite ter alguns usuários hospedados no local e alguns usuários hospedados online.

Às vezes, esse tipo de implantação é conhecido como "domínio dividido" — os usuários o significado de um domínio, por exemplo, contoso.com, são divididos entre usando Skype para Business Server no local e Skype para Business Online da seguinte maneira:

- Os usuários hospedados no local interagem com os servidores locais do Skype for Business

- Os usuários hospedados online interagem com os serviços online do Skype for Business

- Os usuários dos dois ambientes podem colaborar entre si usando o sistema de Mensagens Instantâneas, participando de chamadas em conferência, chamadas VoIP etc.

- O Azure Active Directory Connect é usado para sincronizar seu diretório local com o Office 365

O Active Directory local é autoritativo, o que quer dizer que você deve fazer o seguinte para garantir que os usuários no local e online possam detectar uns aos outros:

- Todos os usuários devem ser criados no Active Directory local primeiro e, em seguida, sincronizados com o Azure AD.

- Se os seus usuários estiverem hospedados no local para o Skype for Business, será necessário habilitá-los para o Skype for Business no local.

- Se os seus usuários estiverem hospedados no local, mas desejarem tirar proveito de alguns recursos online, como a Transmissão de Reunião do Skype, será necessário atribuir uma licença do Skype for Business Online (Plano 2) a eles.

- Se os seus usuários estiverem hospedados no Skype for Business Online, depois que suas contas forem sincronizadas com o Azure AD, será necessário atribuir uma licença do Skype for Business Online (Plano 2) a eles.

- Depois que os usuários do Skype for Business Online tiverem uma licença atribuída a eles, será necessário habilitá-los para o Skype for Business ou para o Enterprise Voice local. Para obter mais informações, consulte [habilitar os usuários para o Enterprise Voice no local](plan-your-phone-system-cloud-pbx-solution/enable-the-users-for-enterprise-voice-on-premises.md). Para obter mais informações sobre os requisitos do Hybrid Voice, consulte [Plan Phone System in Office 365 with on-premises PSTN connectivity in Skype for Business Server](plan-your-phone-system-cloud-pbx-solution/plan-phone-system-with-on-premises-pstn-connectivity.md).

Você saberá mais sobre a configuração do Active Directory nas próximas seções. Mas, primeiro, apresentamos uma visão geral da terminologia e dos acrônimos usados nos diagramas abaixo e em vários tópicos sobre conectividade híbrida:

- PSTN - Rede Telefônica Pública Comutada

- PBX - sistema de telefonia com central privada de comutação telefônica

- Sistema de Telefonia - opção de sistema de telefonia Cloud PBX da Microsoft

- Tronco - linha de telefonia que conecta PBXs à PSTN — um tronco pode usar o protocolo de iniciação de sessão (SIP) — uma Voice over Internet Protocol (VoIP) — ou a tecnologia de multiplexação de divisão de tempo (TDM) mais antiga

- SBC - controlador de borda da sessão - dispositivo que serve como firewall e roteador nas redes telefônicas. Por exemplo, ele fornece segurança, conectividade, interoperabilidade e Qualidade de Serviço.

- Gateway PSTN - um dispositivo que serve como roteador em redes telefônicas, capaz de fazer quase tudo o que um SBC faz, exceto segurança e NAT transversal.

O diagrama a seguir mostra um Skype para configuração do Business "domínio dividido" híbrida. Os usuários A e B estão hospedados online, mas podem ser detectados por usuários locais; os usuários C e D estão hospedados no local, mas podem ser detectados por usuários online.

![Conectividade híbrida do SfB - domínio dividido](../media/c4fc9311-1930-4a58-877f-3c1524dfab5c.png)

Talvez você também conheça o termo "hybrid voice", que se refere a troncos de voz no local que fornecem funcionalidades para usuários hospedados na nuvem. O Hybrid Voice permite a migração para a nuvem enquanto preserva a configuração de voz local. Se você já tem uma implantação do Skype for Business Server, o primeiro passo para habilitar o Hybrid Voice é configurar um ambiente de domínio dividido.

Por exemplo, suponha que sua empresa tem um campo celular grande organização que requer o PBX mínima de suporte voz, mas use Smartphone extensiva. Você pode optar por migrar esses usuários para a nuvem para tirar proveito do Sistema de Telefonia da Microsoft no Office 365 (Cloud PBX). Se a sua empresa também tem uma central de atendimento de grande no local que requer o software avançado e complexos center contato como parte do seu PBX local, você pode optar por deixar esses usuários no local. Os usuários hospedados online e no local têm conectividade PSTN por meio da sua implantação local.

O diagrama a seguir mostra uma implantação do Hybrid Voice do Skype for Business:

![Domínio dividido do SfB com Cloud PBX](../media/5e755772-269e-45ce-8b48-2e06ababfe6c.png)

Para obter mais informações sobre como configurar uma solução de voz híbrida com sua Skype para implantação de servidor de negócios, consulte [Planejar o sistema de telefone no Office 365 com conectividade PSTN local no Skype para Business Server](plan-your-phone-system-cloud-pbx-solution/plan-phone-system-with-on-premises-pstn-connectivity.md).

Você também pode configurar implantações híbridas para integração com o Exchange e SharePoint, ou local com aplicativos do Microsoft Office 365, incluindo o Exchange Online e SharePoint Online. Você também pode configurar uma solução de voz híbrida que não requer uma implantação completa do Skype for Business Server, usando a Cloud Connector Edition. Para obter mais informações sobre todos os Skype para soluções híbridas de negócios e planejamento da mudança para a nuvem, consulte [Skype para soluções híbridas de negócios](skype-for-business-hybrid-solutions.md).

## <a name="infrastructure-requirements"></a>Requisitos de infraestrutura
<a name="BKMK_Infrastructure"> </a>

Para implementar e implantar a conectividade híbrida entre o Skype for Business Server e o Skype for Business Online, configure seu ambiente da seguinte maneira:

- Uma única implantação do Skype para Business Server ou o Lync Server é implantado em uma topologia com suporte no local. Consulte [requisitos de topologia](plan-hybrid-connectivity.md#BKMK_Topology) neste tópico.

    > [!NOTE]
    > Cada domínio SIP que existe no seu ambiente local também deve existir no seu locatário do Office 365 e vice-versa. Você não pode ter alguns domínios SIP online apenas e alguns domínios locais somente. Caso contrário, presença, mensagens Instantâneas e outros recursos não funcionará corretamente.

- Um inquilino do Microsoft Office 365 com o Skype para Business Online habilitado.

    > [!NOTE]
    > Você só pode usar um único locatário para uma configuração híbrida com sua implantação local.

- Skype para ferramentas administrativas do Business Server 2015. (Se você estiver usando o Lync Server 2013 ou o Lync Server 2010, você pode usar as ferramentas administrativas do Lync Server 2013. Para obter mais informações, consulte [Lync Server 2013 híbrido](https://go.microsoft.com/fwlink/p/?LinkId=617360).)

- Azure Active Directory Connect para sincronizar seu diretório local com o Office 365. Para obter mais informações, consulte [Conectar o Active Directory com o Azure Active Directory](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect-accounts-permissions).

    Para oferecer suporte ao logon único no Office 365 de modo que os usuários possam usar as mesmas credenciais de logon que no local, você pode usar os recursos de sincronização de senha do Azure Active Directory (AAD) Connect. É possível também usar Serviços de Federação do Active Directory (AD FS) para login único com o Office 365. 

- Federação habilitada entre a implantação local do Skype for Business e seu locatário do Office 365. Federação permite que os usuários em sua implantação no local para se comunicar com usuários do Office 365 em sua organização. Para obter mais informações, consulte [Configure federation with Skype for Business Online](deploy-hybrid-connectivity/configure-federation-with-skype-for-business-online.md).

- Espaço de endereço SIP compartilhado habilitado. Um endereço SIP é um identificador único para cada usuário em uma rede, semelhante a um número de telefone ou endereço de email. Antes de tentar mover os usuários no local para Skype para Business Online, você precisará configurar seu locatário do Office 365 para compartilhar o espaço de endereço de protocolo de iniciação de sessão (SIP) compartilhados com sua implantação no local. Para obter mais informações, consulte [Configure federation with Skype for Business Online](deploy-hybrid-connectivity/configure-federation-with-skype-for-business-online.md).

## <a name="multi-forest-support"></a>Suporte a várias florestas
<a name="BKMK_MultiForest"> </a>

Os usuários poderão acessar as funcionalidades do Skype for Business em outra floresta se os seguintes requisitos forem atendidos:

- Os usuários são sincronizados corretamente na floresta que hospeda o Skype for Business: em configurações híbridas, isso quer dizer que os usuários devem ser sincronizados como objetos de usuários desabilitados.

- A floresta que hospeda o Skype for Business deve confiar na floresta que contém os usuários.

Para obter detalhes sobre os cenários de híbrida em várias florestas, consulte [Configure um ambiente de várias floresta para o híbrido Skype para negócios](deploy-hybrid-connectivity/configure-a-multi-forest-environment-for-hybrid.md).

## <a name="exchange-co-existence"></a>Coexistência do Exchange
<a name="BKMK_Exchange"> </a>

Para dar suporte à coexistência com o Exchange, considere o seguinte:

- A prática recomendada é mover a caixa de correio do usuário para o Exchange Online antes de mover Skype do usuário for Business residencial.

- Os usuários com caixas de correio locais do Exchange têm suporte com as seguintes limitações conhecidas:

  - Logon do cliente: talvez os usuários precisem fazer logon duas vezes durante o logon do cliente no SfB

  - Server side histórico da conversa, arquivamento, o repositório unificado de contatos, a foto HighRes exige o Exchange 2013 ou posterior e você deve ativar o servidor OAuth comunicação entre servidores. Para obter mais informações, consulte [gerenciar autenticação de servidor-para-servidor (OAuth) e aplicativos de parceiros no Skype para Business Server 2015](https://technet.microsoft.com/en-us/library/jj204817.aspx).

Para obter detalhes sobre a coexistência com o Exchange Server, incluindo os critérios e as limitações de suporte em várias combinações de local e online, consulte [Suporte aos recursos](../plan-your-deployment/integrate-with-exchange/integrate-with-exchange.md#feature_support) em [Plan to integrate Skype for Business and Exchange](../plan-your-deployment/integrate-with-exchange/integrate-with-exchange.md).

## <a name="administrator-credentials"></a>Credenciais do administrador
<a name="BKMK_Credentials"> </a>

Quando você é solicitado a fornecer suas credenciais de administrador, use o nome de usuário e a senha da conta de administrador para o seu locatário do Office 365. Você também usará essas credenciais ao configurar o Azure Active Directory para federação, sincronização de diretórios, logon único e mover os usuários Skype para Business Online.

## <a name="skype-for-business-online-powershell"></a>PowerShell do Skype for Business Online
<a name="BKMK_PowerShell"> </a>

Agora, os administradores têm a capacidade de usar o Windows PowerShell para gerenciar o Skype para Business Online e seu Skype para contas de usuário Business Online. Para fazer isso, você deve primeiro baixar e instalar o Skype para negócios on-line do módulo do conector do Microsoft Download Center. Para obter mais informações sobre como baixar, instalando e usando o Skype para negócios Online módulo de conector e para obter informações detalhadas sobre como usar o Windows PowerShell para gerenciar Skype para negócios Online, consulte [usando o Windows PowerShell para gerenciar Skype para negócios Online](https://technet.microsoft.com/library/dn362831.aspx).

## <a name="skype-for-business-client-support"></a>Suporte ao cliente do Skype for Business
<a name="BKMK_ClientSupport"> </a>

Existem algumas diferenças entre os recursos com suporte em clientes e os recursos disponíveis em ambientes locais e online. Os seguintes clientes compatíveis com Skype para Business Online em uma implantação híbrida:

- Skype for Business

- Lync 2013

- Lync 2010

- Aplicativo Lync Windows Store

- Lync Web App

- Lync Mobile

- Lync para Mac 2011

- Sistema de sala de Lync e Skype para o sistema de sala de negócios

- Lync Basic 2013

- Microsoft Surface Hub

Antes de decidir onde você deseja usuários domésticos em sua organização, você deve consultar a [comparação de recursos do cliente de Desktop do Skype para a empresa](../plan-your-deployment/clients-and-devices/desktop-feature-comparison.md) para determinar o suporte de cliente para as diversas configurações do Skype para Business Server. Consulte também:

- [Planejar clientes e dispositivos](../plan-your-deployment/clients-and-devices/clients-and-devices.md)

- [Comparação de recursos do cliente móvel para Skype para negócios](../plan-your-deployment/clients-and-devices/mobile-feature-comparison.md)

## <a name="topology-requirements"></a>Requisitos de topologia
<a name="BKMK_Topology"> </a>

Para configurar sua implantação para o híbrido com Skype para Business Online, você precisa ter uma das seguintes topologias com suporte:

- Um Skype para implantação de negócios Server 2015 com todos os servidores que executam o Skype para Business Server 2015.

- Uma implantação do Lync Server 2013 com todos os servidores que executam o Lync Server 2013.

    Para a conectividade de voz híbrida, o Servidor de Borda designado como Borda de Federação deve ser o Skype for Business 2015, a Borda também requer um back-end Skype for Business Server. Você deve ter um pool sem usuários.

- Uma implantação do Lync Server 2010 com todos os servidores que executam o Lync Server 2010 com as últimas atualizações acumuladas.

  - O servidor de borda de Federação e o servidor de próximo salto da federação servidor de borda devem estar executando o Lync Server 2010 com as últimas atualizações acumuladas.

  - O Skype para Business Server 2015 ou o Lync Server 2013 Administrative Tools deve ser instalado em pelo menos um servidor ou estação de trabalho de gerenciamento.

- Um misto Skype para implantação Business Server 2015 com as seguintes funções de servidor em pelo menos um site executando o Skype para Business Server 2015 e Lync Server 2013:

  - Pelo menos um servidor Pool Enterprise ou Standard Edition. 

  - O Pool de Diretores associado à federação SIP, se ela existir.

  - O Pool de Borda associado à federação SIP.

- Um misto Skype para implantação Business Server 2015 com as seguintes funções de servidor em pelo menos um site executando o Skype para Business Server 2015 e Lync Server 2010:

  - Pelo menos um servidor Pool Enterprise ou Standard Edition. 

  - O Pool de Diretores associado à federação SIP, se ela existir.

  - O Pool de Borda associado à federação SIP do site.

- Uma implantação mista de Lync Server 2010 e Lync Server 2013 com as seguintes funções de servidor em pelo menos um site executando o Lync Server 2013:

  - Pelo menos um servidor Pool Enterprise ou Standard Edition no site.

  - O Pool de Diretores associado à federação SIP, se ela existir no site.

  - O Pool de Borda associado à federação SIP do site.

## <a name="federation-allowedblocked-lists-requirements"></a>Requisitos das listas de permissões/bloqueios da federação
<a name="BKMK_Federation"> </a>

A lista Domínios permitidos contém domínios com um FQDN (nome de domínio totalmente qualificado) de Borda parceiro configurado. Em alguns casos, elas são referidas como parceiros de Federação do parceiro permitido servidores ordirect. Você deve estar familiarizado com a diferença entre federação aberta e fechado federação, conhecido como lista de domínio do parceiro parceiro descoberta andallowed, respectivamente, em implantações de local.

Os seguintes requisitos devem ser atendidos para configurar com êxito uma implantação híbrida:

- O domínio correspondente deve ser o mesmo configurado para sua implantação local e seu locatário do Office 365. Se a descoberta de parceiros estiver habilitada na implantação local, a federação aberta deverá ser configurada para seu locatário online. Caso contrário, a federação fechada deverá ser configurada para seu locatário online.

- A lista de domínios bloqueados da implantação local deve corresponder exatamente à do seu locatário online.

- A lista de domínios permitidos da implantação local deve corresponder exatamente à do seu locatário online.

- Federação deve ser habilitada para as comunicações externas para o locatário online, que é definida por meio do Skype para painel de controle corporativos Online.

## <a name="dns-settings"></a>Configurações de DNS
<a name="BKMK_DNS"> </a>

Ao criar registros DNS para implantações híbridas, todos os Skype para registros DNS externos corporativos deve apontar para a infraestrutura local. Para obter detalhes sobre registros DNS necessários, consulte [requisitos de DNS para Skype para Business Server 2015](../plan-your-deployment/network-requirements/dns.md).

Além disso será necessário garantir que a resolução DNS descrita na tabela a seguir funciona em sua implantação local:

|Registro DNS  <br/> |Pode ser resolvido por  <br/> |Requisitos de DNS  <br/> |
|:-----|:-----|:-----|
|Registro SRV de DNS para _sipfederationtls._tcp. \<sipdomain.com\> para todas as compatíveis domínios SIP resolver em IP(s) de borda de acesso externo  <br/> |Servidor(es) de borda  <br/> |Habilitar a comunicação federada em uma configuração híbrida. O servidor de borda precisa saber para onde encaminhar o tráfego federado para o domínio SIP que está dividido entre as instalações local e online.  <br/> Deve usar uma correspondência estrita de nomes DNS entre o domínio no nome de usuário e o registro SRV.  <br/> |
|Registro(s) A de DNS para FQDN do serviço de webconferência de borda, como webcon.contoso.com, que resolve IP(s) de borda de webconferência  <br/> |Rede corporativa interna conectados nos computadores dos usuários  <br/> |Habilitar usuários online para apresentar ou visualizar conteúdo em reuniões hospedadas localmente. O conteúdo inclui arquivos do PowerPoint, quadros de comunicações, votações e observações compartilhadas.   <br/> |

Dependendo de como o DNS está configurado na sua organização, talvez seja necessário adicionar esses registros à zona DNS hospedada interna para os domínios SIP correspondentes para proporcionar resolução de DNS interna para esses registros.

[!NOTE] _sipfederationtls._tcp. \<sipdomain.com\> resolução de registro SRV do servidor de borda é necessária para a configuração híbrida. Se o servidor de borda não pode resolver esses registros, os usuários no local não poderão ver as informações de presença ou se comunicar com usuários online.

## <a name="firewall-considerations"></a>Considerações sobre o firewall
<a name="BKMK_Firewall"> </a>

Os computadores de sua rede devem ser capazes de realizar pesquisas DNS padrão na Internet. Se esses computadores puderem acessar os sites padrão da Internet, sua rede atenderá a esse requisito.

Dependendo do local do seu centro de dados do Microsoft Online Services, você também deve configurar os dispositivos de firewall de rede para aceitar conexões com base em nomes de domínio de caractere curinga (por exemplo, todo o tráfego da \*. outlook.com). Se dos firewalls da organização não oferecer suporte a configurações de nome de curinga, você terá de determinar manualmente os intervalos de endereços IP que você gostaria de permitir e as portas especificadas.

Para obter mais informações, veja [URLs e intervalos de endereço IP do Office 365](https://go.microsoft.com/fwlink/p/?LinkId=252942).

## <a name="port-and-protocol-requirements"></a>Requisitos de porta e protocolo
<a name="BKMK_Ports"> </a>

Além dos requisitos de porta para a comunicação interna, você também deve configurar as portas a seguir para habilitar a conectividade híbrida.


|**Protocolo**|**TCP ou UDP**|**IP de origem**|**IP de destino**|**Porta de origem**|**Porta de Destino**|**Observações**|
|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
|SIP (MTLS)  <br/> |TCP  <br/> |Borda de Acesso  <br/> |Office 365  <br/> |Qualquer  <br/> |5061  <br/> |Sinalização  <br/> |
|SIP (MTLS)  <br/> |TCP  <br/> |Office 365  <br/> |Borda de Acesso  <br/> |Qualquer  <br/> |5061  <br/> |Sinalização  <br/> |
|STUN  <br/> |TCP  <br/> |Borda A/V  <br/> |Office 365  <br/> |50000-59999  <br/> |443  <br/> |Abertas para sessões de áudio, vídeo e compartilhamento de aplicativos  <br/> |
|STUN  <br/> |TCP  <br/> |Office 365  <br/> |Borda A/V  <br/> |50000-59999  <br/> |443  <br/> |Abertas para sessões de áudio, vídeo e compartilhamento de aplicativos  <br/> |
|STUN  <br/> |UDP  <br/> |Borda A/V  <br/> |Office 365  <br/> |3478  <br/> |3478  <br/> |Abertas para sessões de áudio, vídeo  <br/> |
|STUN  <br/> |UDP  <br/> |Office 365  <br/> |Borda A/V  <br/> |3478  <br/> |3478  <br/> |Abertas para sessões de áudio, vídeo  <br/> |

Para obter mais informações sobre a porta e firewall de planejamento para o servidor de borda, consulte [requisitos de ambiente de servidor de borda no Skype para Business Server 2015](../plan-your-deployment/edge-server-deployments/edge-environmental-requirements.md). Consulte também [Port and protocol requirements for servers](../plan-your-deployment/network-requirements/ports-and-protocols.md) e o [Diagrama de cargas de trabalho dos protocolos](https://go.microsoft.com/fwlink/p/?LinkId=550989).

## <a name="user-accounts-and-data"></a>Dados e contas de usuário
<a name="BKMK_UserAccounts"> </a>

Em uma implantação híbrida, qualquer usuário que você deseja hospedar online deve primeiro ser criado na implantação do local, para que a conta de usuário é criada nos serviços de domínio Active Directory. Em seguida, você pode mover o usuário para Skype para negócios Online, que irá mover a lista de contatos do usuário.

Ao sincronizar contas de usuário entre sua implantação no local e online inquilino usando AAD conectar, você precisa sincronizar as contas do AD para todos os Skype para usuários corporativos ou o Lync em sua organização, mesmo se os usuários não são movidos para online. Se você não sincronizar todos os usuários, a comunicação entre os usuários online e locais em sua organização poderá não funcionar como esperado.

> [!IMPORTANT]
> Gerenciamento de todos os usuários, incluindo o usuário move entre locais e do Skype para negócios Online, deve ser feito usando a última versão instalada das ferramentas administrativas. As ferramentas administrativas devem ser instaladas em um servidor separado que possui acesso se conectam a implantação existente do local e à Internet. O cmdlet para mover usuários de sua implantação no local para Skype para negócios Online, [Move-CsUser](https://docs.microsoft.com/powershell/module/skype/move-csuser?view=skype-ps), deve ser executado em Ferramentas administrativas conectadas à sua implantação no local. Para obter mais informações sobre como mover usuários, consulte [mover os usuários no local para Skype para negócios Online](deploy-hybrid-connectivity/move-users-from-on-premises-to-skype-for-business-online.md).

> [!IMPORTANT]
> Se o usuário foi criado com o portal online do Office 365, a conta de usuário não será sincronizada com o Active Directory local e o usuário não existirá no Active Directory local. Se você já criou usuários no locatário online e deseja configurar a implantação híbrida com uma implantação local, veja Mover usuários de online para local.

> [!NOTE]
> Se você estiver atualmente um Skype para cliente Business Online que possui usuários habilitados para Skype para Business Online que não tiverem sido habilitados em uma implantação local, consulte [mover usuários do Skype para negócios on-line para no local](deploy-hybrid-connectivity/move-users-from-skype-for-business-online-to-on-premises.md).

Você também deve considerar os seguintes problemas relacionados ao usuário ao se planejar para uma implantação híbrida.

- **Contatos do usuário** O limite para contatos do Skype para usuários corporativos Online é 250. Todos os contatos além desse número serão removidos da lista de contatos do usuário quando a conta é movida para Skype para negócios Online.

- **Mensagens instantâneas e presença** Listas de contatos do usuário, grupos e listas de controle de acesso (ACLs) são migradas com a conta de usuário.

- **Dados de conferência, o conteúdo das reuniões e reuniões agendadas** Este conteúdo não é migrado com a conta de usuário. Os usuários devem reagendar reuniões depois que suas contas são migradas para o Skype para negócios Online. O serviço de migração de reunião irá fazer isso automaticamente ao migrar de um Skype para Business server para Skype para equipes ou Business Online, consulte [usando o serviço de migração de reunião](https://docs.microsoft.com/en-us/skypeforbusiness/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms).


## <a name="user-policies-and-features"></a>Recursos e políticas de usuário
<a name="BKMK_UserPolicies"> </a>

- Em um ambiente híbrido, os usuários podem estar habilitados para o sistema de mensagens instantâneas e conferências, no local (reuniões) ou online; porém, não para os dois ao mesmo tempo.

- **Suporte do cliente** Alguns usuários podem exigir uma nova versão do cliente quando eles são movidos para Skype para negócios Online. Para o Office Communications Server 2007 R2, os usuários devem ser movidos para um Skype para pool Business Server ou o Lync Server 2013 antes da migração para o Skype para negócios Online.

- **Local políticas e configuração (não-usuários)** Online e políticas exigem configuração separado no local. Você não pode definir políticas globais que se apliquem a ambas.


