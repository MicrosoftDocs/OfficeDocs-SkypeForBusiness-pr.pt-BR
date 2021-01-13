---
title: Requisitos ambientais do Skype for Business Server 2015
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 2/15/2018
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 4812c444-2546-48d7-9ca7-b71fce508ed8
description: 'Resumo: Configure seus requisitos que não são de servidor para o Skype for Business Server 2015. Há uma variedade de coisas que você vai querer configurar antes de fazer sua implantação, incluindo Active Directory, DNS, Certificados e Fileshares.'
ms.openlocfilehash: 83e01cec8bea5a45debadcf8ef9167ddd53b6a46
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49832131"
---
# <a name="environmental-requirements-for-skype-for-business-server-2015"></a>Requisitos ambientais do Skype for Business Server 2015
 
**Resumo:** Configure seus requisitos que não são de servidor para o Skype for Business Server 2015. Há uma variedade de coisas que você vai querer configurar antes de fazer sua implantação, incluindo Active Directory, DNS, Certificados e Fileshares.
  
Qual é um requisito ambiental para o Skype for Business Server 2015? Bem, colocamos tudo o que não está diretamente relacionado ao servidor neste tópico, para que você não tenha que clicar tanto. Se você estiver procurando por pré-requisitos de servidor, poderá verificar os requisitos de servidor [](../../plan-your-deployment/network-requirements/network-requirements.md) para o documento do [Skype for Business Server 2015.](server-requirements.md) O planejamento de rede também é documentado separadamente. Caso contrário, este é o que temos neste artigo:
  
- [Active Directory](environmental-requirements.md#AD)
  
- [Domain Name System (DNS)](environmental-requirements.md#DNS)
  
- [Certificados](environmental-requirements.md#Certs)
  
- [Compartilhamento de Arquivos](environmental-requirements.md#Fileshare)
  
## <a name="active-directory"></a>Active Directory
<a name="AD"> </a>

Embora muitos dados de configuração para servidores e serviços sejam armazenados no armazenamento de Gerenciamento Central do Skype for Business Server 2015, algumas coisas ainda estão armazenadas no Active Directory:
  
|**Objetos do Active Directory**|**Tipos de objeto**|
|:-----|:-----|
|Extensões de esquema  <br/> |Extensões do objeto do usuário  <br/> |
||Extensões para Lync Server 2013 e Lync Server 2010, para manter a compatibilidade com versões anteriores com suporte.  <br/> |
|Dados  <br/> |URI do SIP do usuário e outras configurações do usuário  <br/> |
||Objetos de contato para aplicativos (como o aplicativo Grupo de Resposta e o aplicativo Atendente de Conferência).  <br/> |
||Dados publicados para compatibilidade com compatibilidade.  <br/> |
||Um ponto de controle de serviço (SCP) para o armazenamento de Gerenciamento Central.  <br/> |
||Conta de Autenticação Kerberos (um objeto de computador opcional).  <br/> |
   
### <a name="os-for-domain-controllers"></a>Sistema operacional para controladores de domínio

Então, qual sistema operacional do controlador de domínio pode ser usado? Temos a seguinte lista:

- Windows Server 2019 (você deve ter a Atualização Cumulativa 5 ou posterior do Skype for Business Server 2015)
  
- Windows Server 2016
    
- Windows Server 2012 R2
    
- Windows Server 2012
    
- Windows Server 2008 R2
    
- Windows Server 2008
    
Agora, o nível funcional de domínio de qualquer domínio em que você implanta o Skype for Business Server 2015, e o nível funcional da floresta de qualquer floresta na qual você implanta o Skype for Business Server 2015, deve ser um dos seguintes:

- Windows Server 2019 (você deve ter a Atualização Cumulativa 5 ou posterior do Skype for Business Server 2015)
  
- Windows Server 2016
    
- Windows Server 2012 R2
    
- Windows Server 2012
    
- Windows Server 2008 R2
    
- Windows Server 2008
    
- Windows Server 2003
    
É possível ter controladores de domínio somente leitura nesses ambientes? Claro, desde que também haja controladores de domínio writable disponíveis no mesmo site que o Skype for Business Server.
  
Agora, é importante saber que o Skype for Business Server 2015 não dá suporte a domínios com rótulo único. O que são eles? Se você tiver um domínio raiz rotulado como contoso.local, tudo bem. Se você tiver um domínio raiz que tenha apenas o nome local, isso não funcionará e não terá suporte como resultado. Um pouco mais sobre isso foi escrito [neste artigo da Base de Dados de Conhecimento.](https://support.microsoft.com/kb/300684/en-us)
  
O Skype for Business Server 2015 também não dá suporte à renomeação de domínios. Se você realmente precisa fazer isso, precisará desinstalar o Skype for Business Server 2015, renomear o domínio e reinstalar o Skype for Business Server 2015.
  
Por fim, você pode estar lidando com um domínio com um ambiente bloqueado do AD DS, e tudo bem. Temos mais informações sobre como implantar o Skype for Business Server 2015 nesse tipo de ambiente nos documentos de Implantação.
  
### <a name="ad-topologies"></a>Topologias do AD

As topologias com suporte do Skype for Business Server 2015 são:
  
- Floresta única com domínio único
    
- Floresta única com uma única árvore e vários domínios
    
- Floresta única com várias árvores e namespaces não contíguos
    
- Várias florestas em uma topologia de floresta central
    
- Várias florestas em uma topologia de floresta de recursos
    
- Várias florestas em uma topologia de floresta de recursos do Skype for Business com o Exchange Online
    
- Várias florestas em uma topologia de floresta de recursos com o Skype for Business Online e o Azure Active Directory Connect
    
Temos diagramas e descrições para ajudá-lo a determinar qual topologia você tem em seu ambiente ou o que você pode precisar configurar antes de instalar o Skype for Business Server 2015. Para manter a simples, também estamos incluindo uma chave:
  
![É uma chave para os ícones usados para diagramas de topologia do Skype for Business](../../media/cc0dbc17-cf81-4b79-bf99-4614cc6828a0.png)
  
#### <a name="single-forest-with-single-domain"></a>Floresta única com domínio único

![Diagrama de floresta única do Active Directory com um único domínio](../../media/24921a0b-3a3e-4bad-8427-49300e2e3f7a.png)
  
Não é mais fácil do que isso, é uma floresta de domínio único, é uma topologia comum.
  
#### <a name="single-forest-with-a-single-tree-and-multiple-domains"></a>Floresta única com uma única árvore e vários domínios

![Uma única floresta, uma única árvore e um diagrama de domínios mutiple](../../media/63b9f0dd-6bac-4ba9-ae68-8be032d09dcb.png)
  
Este diagrama mostra uma única floresta, novamente, mas também tem um ou mais domínios filhos (há três neste exemplo específico). Portanto, o domínio no qual os usuários são criados pode ser diferente do domínio em que o Skype for Business Server 2015 está implantado. Por que se preocupar com isso? É importante lembrar que, quando você implanta um pool de front-end do Skype for Business Server, todos os servidores nesse pool precisam estar em um único domínio. Você pode ter administração entre domínios por meio do suporte do Skype for Business Server a grupos de administradores universais do Windows.
  
De volta ao diagrama acima, você pode ver que os usuários de um domínio podem acessar pools do Skype for Business Server do mesmo domínio ou de domínios diferentes, mesmo se esses usuários estão em um domínio filho.
  
#### <a name="single-forest-with-multiple-trees-and-disjoint-namespaces"></a>Floresta única com várias árvores e namespaces não contíguos

![Uma única floresta, várias árvores e diagrama de namespaces não adjacentes](../../media/5ede77a1-f5d2-499c-a2c8-d02f3c2f7cd7.png)
  
Pode ser que você tenha uma topologia semelhante a este diagrama, onde você tem uma floresta, mas dentro dessa floresta há vários domínios, com namespaces do AD separados. Se esse for o caso, este diagrama é uma boa ilustração, pois temos usuários em três domínios diferentes acessando o Skype for Business Server 2015. Linhas sólidas indicam que estão acessando um pool do Skype for Business Server em seu próprio domínio, enquanto uma linha tracejada indica que eles estão indo para um pool em uma árvore diferente.
  
Como você pode ver, os usuários no mesmo domínio, na mesma árvore ou até mesmo em uma árvore diferente podem acessar pools com êxito.
  
#### <a name="multiple-forests-in-a-central-forest-topology"></a>Várias florestas em uma topologia de floresta central

![Várias florestas em um diagrama de topologia de floresta central](../../media/fec40746-4254-4c84-86b9-aad4a616ea2f.png)
  
O Skype for Business Server 2015 dá suporte a várias florestas configuradas em uma topologia de floresta central. Se você não tiver certeza de que é o que você tem, a floresta central na topologia usa objetos para representar usuários nas outras florestas e hospeda contas de usuário para todos os usuários na floresta.
  
Como isso funciona? Bem, um produto de sincronização de diretório (como o Forefront Identity Manager ou FIM) gerencia as contas de usuário da sua organização durante toda a sua existência. Quando uma conta é criada ou excluída de uma floresta, essa alteração é sincronizada até o contato correspondente na floresta central.
  
Claramente, se a infraestrutura do AD estiver no local, mudar para essa topologia pode não ser fácil, mas se você já estiver lá ou ainda planejar sua infraestrutura de floresta, essa pode ser uma boa opção. Você pode centralizar sua implantação do Skype for Business Server 2015 em uma única floresta, enquanto os usuários podem pesquisar, comunicar e exibir a presença de outros usuários em qualquer floresta. Todas as atualizações de contatos do usuário são tratadas automaticamente com o software de sincronização.
  
#### <a name="multiple-forests-in-a-skype-for-business-resource-forest-topology"></a>Várias florestas em uma topologia de floresta de recursos do Skype for Business
<a name="BKMK_multipleforestopology"> </a>

![Várias florestas em um diagrama de topologia de floresta de recursos](../../media/41efa3b6-d9e6-47df-992b-fefcfc39a80d.png)
  
Uma topologia de floresta de recursos também é suportada; é onde uma floresta é dedicada a executar seus aplicativos de servidor, como o Microsoft Exchange Server e o Skype for Business Server 2015. Essas florestas de recursos também hospedam uma representação sincronizada de objetos de usuário ativos, mas nenhuma conta de usuário habilitada para logon. Portanto, a floresta de recursos é um ambiente de serviços compartilhados para outras florestas nas quais os objetos de usuário residem, e eles têm uma relação de confiança no nível da floresta com a floresta de recursos.
  
Observe que o Exchange Server pode ser implantado na mesma floresta de recursos que o Skype for Business Server ou em uma floresta diferente.
  
Para implantar o Skype for Business Server 2015 nesse tipo de topologia, crie um objeto de usuário desabilitado na floresta de recursos para cada conta de usuário nas florestas de usuários (se o Microsoft Exchange Server já estiver no ambiente, isso pode ser feito para você). Em seguida, você precisará de uma ferramenta de sincronização de diretórios (como o Forefront Identity Manager ou FIM) para gerenciar contas de usuário durante seu ciclo de vida.
  
#### <a name="multiple-forests-in-a-skype-for-business-resource-forest-topology-with-exchange-online"></a>Várias florestas em uma topologia de floresta de recursos do Skype for Business com o Exchange Online
<a name="BKMK_multipleforestopology"> </a>

Essa topologia é semelhante à topologia descrita em [Várias florestas em uma topologia de floresta](environmental-requirements.md#BKMK_multipleforestopology)de recursos do Skype for Business.
  
Nessa topologia, há uma ou mais florestas de usuários, e o Skype for Business Server é implantado em uma floresta de recursos dedicada. O Exchange Server pode ser implantado localmente na mesma floresta de recursos ou em uma floresta diferente e configurado para híbrido com o Exchange Online, ou os serviços de email podem ser fornecidos exclusivamente pelo Exchange Online para as contas locais. Não há diagrama disponível para essa topologia.
  
#### <a name="multiple-forests-in-a-resource-forest-topology-with-skype-for-business-online-and-azure-active-directory-connect"></a>Várias florestas em uma topologia de floresta de recursos com o Skype for Business Online e o Azure Active Directory Connect
<a name="BKMK_multipleforestopology"> </a>

![Mostra duas florestas do AD, uma floresta de usuário e uma floresta de recursos. As duas florestas têm uma relação de confiança. Eles são sincronizados com o Microsoft 365 ou o Office 365 usando o Azure AD Connect. Todos os usuários estão habilitados para o Skype for Business por meio do Microsoft 365 ou Office 365.](../../media/6d54558d-8786-4ebf-90f6-55ae3fdb5ae7.jpg)
  
Com esse cenário, há várias florestas locais, com uma topologia de floresta de recursos. Há uma relação de confiança total entre as florestas do Active Directory. A ferramenta Azure Active Directory Connect é usada para sincronizar contas entre as florestas de usuários locais e o Microsoft 365 ou Office 365.
  
 A organização também tem o Microsoft 365 ou o Office 365 e usa o [Azure Active Directory Connect](https://go.microsoft.com/fwlink/p/?LinkId=614836) para sincronizar suas contas locais com o Microsoft 365 ou o Office 365. Os usuários habilitados para o Skype for Business estão habilitados por meio do Microsoft 365 ou Office 365 e do Skype for Business Online. O Skype for Business Server não é implantado no local.
  
A autenticação de login único é fornecida por um farm dos Serviços de Federação do Active Directory localizado na floresta do usuário.
  
Neste cenário, há suporte para implantar o Exchange local, o Exchange Online, uma solução híbrida do Exchange ou para não ter o Exchange implantado. (O diagrama mostra apenas o Exchange local, mas as outras soluções do Exchange também são totalmente suportadas.)
  
#### <a name="multiple-forests-in-a-resource-forest-topology-with-hybrid-skype-for-business"></a>Várias florestas em uma topologia de floresta de recursos com o Skype for Business híbrido
<a name="BKMK_multipleforestopology"> </a>

Nesse cenário, há uma ou mais florestas de usuários locais, e o Skype for Business é implantado em uma floresta de recursos dedicada e é configurado para o modo híbrido com o Skype for Business Online. O Exchange Server pode ser implantado no local na mesma floresta de recursos ou em uma floresta diferente e pode ser configurado para híbrido com o Exchange Online. Como alternativa, os serviços de email podem ser fornecidos exclusivamente pelo Exchange Online para as contas locais.
  
Para obter mais informações, [consulte Configurar um ambiente de várias florestas para o Skype for Business híbrido.](../../skype-for-business-hybrid-solutions/deploy-hybrid-connectivity/configure-a-multi-forest-environment-for-hybrid.md)
  
## <a name="domain-name-system-dns"></a>Domain Name System (DNS)
<a name="DNS"> </a>

O Skype for Business Server 2015 requer DNS, pelos seguintes motivos:
  
- O DNS permite que o Skype for Business Server 2015 descubra pools ou servidores internos, permitindo comunicações entre servidores.
    
- O DNS permite que os máquinas cliente descubram o pool de Front-End ou o servidor Standard Edition que está sendo usado para transações SIP.
    
- Ele associa URLs simples para conferências com os servidores que hospedam essas conferências.
    
- O DNS permite que usuários externos e máquinas clientes se conectem aos seus Servidores de Borda, ou ao proxy reverso HTTP, para mensagens instantâneas (IM) ou conferências.
    
- Ele permite que os dispositivos de comunicações unificadas (UC) que não estão conectados descubram o pool de Front-End ou o servidor Standard Edition que está executando o serviço Web de Atualização de Dispositivo para obter atualizações e enviar logs.
    
- O uso do DNS permite que os clientes móveis descubram automaticamente recursos de serviços Web sem exigir que os usuários insiram URLs manualmente nas configurações do dispositivo.
    
- E ele é usado no balanceamento de carga DNS.
    
É importante observar que o Skype for Business Server 2015 não dá suporte a IDNs (nomes de domínio internacionalizados).
  
E é extremamente importante lembrar que qualquer nome no DNS seja idêntico ao nome do computador configurado em qualquer servidor que está sendo usado pelo Skype for Business Server 2015. Especificamente, não podemos ter nomes curtos no ambiente e é necessário ter FQDNs para o Construtor de Topologias.
  
Isso parecerá lógico para qualquer computador que já tenha ingressado em um domínio, mas se você tiver um Servidor de Borda que não tenha ingressado no seu domínio, ele poderá ter um nome curto padrão, sem sufixo de domínio. Certifique-se de que esse não seja o caso, no DNS ou no Servidor de Borda, ou em qualquer servidor ou pool do Skype for Business Server 2015, nesse caso.
  
E, definitivamente, não use caracteres Unicode ou sublinhados. Caracteres padrão (que são A-Z, a-z, 0-9 e hífens) são os únicos que serão suportados por DNS externo e autoridades de certificação públicas (você precisará atribuir FQDNs ao SN no certificado, não se esqueça), portanto, você poupará muita coisa se nomear com isso em mente.
  
Para saber mais sobre os requisitos de DNS para rede, confira a seção [Rede](../../plan-your-deployment/network-requirements/network-requirements.md) da nossa documentação de Planejamento.
  
## <a name="certificates"></a>Certificados
<a name="Certs"> </a>

Uma das coisas mais importantes que você pode fazer antes de implantar é garantir que seus certificados estão em ordem. O Skype for Business Server 2015 precisa de uma PKI (infraestrutura de chave pública) para conexões TLS e MTLS (mutual transport layer security). Basicamente, para se comunicar com segurança de forma padronizada, o Skype for Business Server usa certificados emitidos por autoridades de certificação (CAs).
  
Estas são algumas das coisas para as que o Skype for Business Server 2015 usa certificados:
  
- Conexões TLS entre clientes e servidores
    
- Conexões MTLS entre servidores
    
- Federação usando a descoberta automática de parceiros no DNS
    
- Acesso de usuários remotos a IM (mensagens instantâneas)
    
- Acesso de usuário externo a sessões de áudio/vídeo (AV), compartilhamento de aplicativos e conferência
    
- Comunicação com aplicativos Web e Outlook Web Access (OWA)
    
Portanto, o planejamento de certificados é necessário. Agora, vamos ver uma lista de algumas coisas que você precisa ter em mente ao solicitar certificados:
  
- Todos os certificados de servidor devem oferecer suporte à autorização de servidor (EKU de servidor).
    
- Todos os certificados de servidor devem conter um CDP (Ponto de Distribuição de CRL).
    
- Todos os certificados devem ser assinados usando um algoritmo de assinatura suportado pelo sistema operacional. O Skype for Business Server 2015 dá suporte ao pacote SHA-1 e SHA-2 de tamanhos digest (224, 256, 384 e 512 bits) e atende ou excede os requisitos do sistema operacional.
    
- O registro automático é suportado para servidores internos que executam o Skype for Business Server 2015.
    
- O registro automático não é suportado para Servidores de Borda do Skype for Business Server 2015.
    
- Quando você envia uma solicitação de certificado baseado em web para uma AC Windows Server 2003, você deve submete-la de um computador que esteja executando Windows Server 2003 com SP2 ou Windows XP.
    
> [!NOTE]
> Embora o KB922706 suporte para resolver problemas com o registro de certificados web em um registro da Web de Serviços de Certificados do Windows Server 2003, ele não possibilita o uso do Windows Server 2008, Windows Vista ou Windows 7 para solicitar um certificado de uma CA do Windows Server 2003. 
  
> [!NOTE]
> O uso do algoritmo de assinatura RSASSA-PSS não é compatível e pode levar a erros em problemas de logon e encaminhamento de chamada, entre outros problemas. 

> [!NOTE]
> O Skype for Business Server 2015 não dá suporte a certificados CNG.
  
- Os comprimentos de chave de criptografia de 1024, 2048 e 4096 são suportados. Comprimentos de chave maiores que 2048 são recomendados.
    
- O algoritmo de assinatura de hash ou digest padrão é RSA. Os ECDH_P256, ECDH_P384 e ECDH_P521 também são suportados.
    
Portanto, é muito sobre o que pensar e, definitivamente, há uma variedade de níveis de conforto com a solicitação de certificados de uma AC. Vamos dar mais algumas orientações abaixo para tornar seu planejamento o mais indolor possível.
  
### <a name="certificates-for-your-internal-servers"></a>Certificados para seus servidores internos

Você precisará de certificados para a maioria dos seus servidores internos e, provavelmente, você os obterá de uma AC interna (que está localizada em seu domínio). Se quiser, você pode solicitar esses certificados de uma CA externa (localizada na Internet). Se você estiver se perguntando para qual AC pública você deve ir, confira a lista de parceiros de [certificados de Comunicações](/SkypeForBusiness/certification/services-ssl) Unificadas.
  
Você também precisará de certificados quando o Skype for Business Server 2015 se comunicar com outros aplicativos e servidores, como o Microsoft Exchange Server. Isso, obviamente, precisará ser um certificado que esses outros aplicativos e servidores possam usar de forma com suporte. O Skype for Business Server 2015 e outros produtos da Microsoft suportam o protocolo OAuth (Open Authorization) para autenticação e autorização de servidor para servidor. Se você estiver interessado nisso, temos um artigo de planejamento adicional para o OAuth e o Skype for Business Server 2015.
  
O Skype for Business Server 2015 também inclui suporte para (sem a necessidade) de certificados assinados usando a função de hash criptográfico SHA-256. Para dar suporte ao acesso externo usando SHA-256, o certificado externo precisa ser emitido por uma CA pública usando SHA-256.
  
Para tentar manter as coisas simples, colocamos os requisitos de certificado para servidores Standard Edition, pools de front-end e outras funções, nas tabelas a seguir, com o contoso.com fictício sendo usado como exemplos (você provavelmente estará usando algo mais para seu ambiente). Todos esses certificados são certificados de servidor Web padrão, com chaves privadas que não são exportáveis. Algumas coisas adicionais a observar:
  
- O EKU (uso de chave aprimorado do servidor) é configurado automaticamente quando você usa o assistente de certificado para solicitar certificados.
    
- Cada nome amigável de certificado deve ser exclusivo no armazenamento do computador.
    
- De acordo com os nomes de exemplo abaixo, se você configurou o sipinternal.contoso.com ou o sipexternal.contoso.com em seu DNS, eles precisarão ser adicionados ao SAN (Nome Alternativo da Assunto) do certificado.
    
Certificados para servidores Standard Edition:
  
|**Certificado**|**Nome do assunto/Nome comum**|**Nome alternativo da entidade**|**Exemplo**|**Comments**|
|:-----|:-----|:-----|:-----|:-----|
|Padrão  <br/> |FQDN do pool  <br/> |FQDN do pool e FQDN do servidor  <br/> Se você tiver vários domínios SIP e tiver habilitado a configuração automática do cliente, o assistente de certificados detectará e adicionará os FQDNs de cada domínio SIP aceito.  <br/> Se esse pool é o servidor de logon automático para clientes, e a combinação estrita do Sistema de Nome de Domínio (DNS) é exigida na política do grupo, também é preciso de entradas para o sip.sipdomain (para cada domínio de SIP que você tiver).  <br/> |SN=se01.contoso.com; SAN=se01.contoso.com  <br/> Se esse pool é o servidor de logon automático para clientes, e se a combinação estrita de DNS for exigida na política do grupo, também serão precisos: SAN=sip.contoso.com; SAN=sip.fabrikam.com  <br/> |No servidor Standard Edition, o servidor FQDN é o mesmo que o pool FQDN.  <br/> O assistente detecta todos os domínios SIP especificados durante a instalação e os adiciona automaticamente como nomes alternativos de assunto.  <br/> Você também pode usar esse certificado para autenticação de servidor para servidor.  <br/> |
|Web interna  <br/> |FQDN do servidor  <br/> |Cada um dos seguintes:  <br/> • FQDN da Web interno (que é o mesmo que o FQDN do servidor)  <br/> E  <br/> • Conheça URLs simples  <br/> • URL simples de discagem  <br/> • URL simples de administração  <br/> OU  <br/> • Uma entrada curinga para as URLs simples  <br/> |SN=se01.contoso.com; SAN=se01.contoso.com; SAN=meet.contoso.com; SAN=meet.fabrikam.com; SAN=dialin.contoso.com; SAN=admin.contoso.com  <br/> Como usar um certificado curinga:  <br/> SN=se01.contoso.com; SAN=se01.contoso.com; SAN= \* .contoso.com  <br/> |Não é possível substituir o FQDN da Web Interno no Construtor de Topologias.  <br/> Se tiver várias URLs Reunir simples, você terá que incluir todas elas como SANs.  <br/> As entradas curinga são suportadas pelas entradas de URL simples.  <br/> |
|Web externa  <br/> |FQDN do servidor  <br/> |Cada um dos seguintes:  <br/> • FQDN da Web Externa  <br/> E  <br/> • URL simples de discagem  <br/> • Conheça URLs simples por domínio SIP  <br/> OU  <br/> • Uma entrada curinga para as URLs simples  <br/> |SN=se01.contoso.com; SAN=webcon01.contoso.com; SAN=meet.contoso.com; SAN=meet.fabrikam.com; SAN=dialin.contoso.com  <br/> Como usar um certificado coringa:  <br/> SN=se01.contoso.com; SAN=webcon01.contoso.com; SAN= \* .contoso.com  <br/> |Se tiver várias URLs Reunir simples, você terá que incluir todas elas como nomes alternativos de assunto.  <br/> As entradas curinga são suportadas pelas entradas de URL simples.  <br/> |
   
Certificados para servidores front-end em um pool de front-end enterprise edition:
  
|**Certificado**|**Nome do assunto/Nome comum**|**Nome alternativo da entidade**|**Exemplo**|**Comments**|
|:-----|:-----|:-----|:-----|:-----|
|Padrão  <br/> |FQDN do pool  <br/> |FQDN do pool e FQDN do servidor  <br/> Se você tiver vários domínios SIP e tiver habilitado a configuração automática do cliente, o assistente de certificados detectará e adicionará os FQDNs de cada domínio SIP aceito.  <br/> Se esse pool é o servidor de logon automático para clientes, e a combinação estrita do Sistema de Nome de Domínio (DNS) é exigida na política do grupo, também é preciso de entradas para o sip.sipdomain (para cada domínio de SIP que você tiver).  <br/> |SN=eepool.contoso.com; SAN=eepool.contoso.com; SAN=ee01.contoso.com  <br/> Se esse pool é o servidor de logon automático para clientes, e se a combinação estrita de DNS for exigida na política do grupo, também serão precisos: SAN=sip.contoso.com; SAN=sip.fabrikam.com  <br/> |O assistente detecta quaisquer domínios SIP especificados durante a instalação e os adiciona automaticamente ao nome alternativo para a entidade.  <br/> Você também pode usar esse certificado para autenticação de servidor para servidor.  <br/> |
|Web interna  <br/> |FQDN do pool  <br/> |Cada um dos seguintes:  <br/> • FQDN da Web interno (que NÃO é o mesmo que o FQDN do servidor)  <br/> • FQDN do servidor  <br/> • FQDN do pool do Skype for Business  <br/> E  <br/> • Conheça URLs simples  <br/> • URL simples de discagem  <br/> • URL simples de administração  <br/> OU  <br/> • Uma entrada curinga para as URLs simples  <br/> |SN=ee01.contoso.com; SAN=ee01.contoso.com; SAN=meet.contoso.com; SAN=meet.fabrikam.com; SAN=dialin.contoso.com; SAN=admin.contoso.com  <br/> Como usar um certificado curinga:  <br/> SN=ee01.contoso.com; SAN=ee01.contoso.com; SAN= \* .contoso.com  <br/> |Se tiver várias URLs Reunir simples, você terá que incluir todas elas como nomes alternativos de assunto.  <br/> As entradas curinga são suportadas pelas entradas de URL simples.  <br/> |
|Web externa  <br/> |FQDN do pool  <br/> |Cada um dos seguintes:  <br/> • FQDN da Web Externa  <br/> E  <br/> • URL simples de discagem  <br/> • URL simples de administração  <br/> OU  <br/> • Uma entrada curinga para as URLs simples  <br/> |SN=ee01.contoso.com; SAN=webcon01.contoso.com; SAN=meet.contoso.com; SAN=meet.fabrikam.com; SAN=dialin.contoso.com  <br/> Como usar um certificado curinga:  <br/> SN=ee01.contoso.com; SAN=webcon01.contoso.com; SAN= \* .contoso.com  <br/> |Se tiver várias URLs Reunir simples, você terá que incluir todas elas como nomes alternativos de assunto.  <br/> As entradas curinga são suportadas pelas entradas de URL simples.  <br/> |
   
Certificados para o Diretor:
  
|**Certificado**|**Nome do assunto/Nome comum**|**Nome alternativo da entidade**|**Exemplo**|
|:-----|:-----|:-----|:-----|
|Padrão  <br/> |Director pool  <br/> |FQDN do Diretor, FQDN do pool de Diretores.  <br/> Se esse pool for o servidor de logon automático para clientes e a correspondência estrita de DNS for necessária na política de grupo, você também precisará de entradas para sip.sipdomain (para cada domínio SIP que você tiver).  <br/> |pool.contoso.com; SAN=dir01.contoso.com  <br/> Se esse pool de Diretor for o servidor de logon automático para clientes, e se a combinação estrita de DNS for exigida na política do grupo, também serão precisos: SAN=sip.contoso.com; SAN=sip.fabrikam.com  <br/> |
|Web interna  <br/> |FQDN do servidor  <br/> |Cada um dos seguintes:  <br/> • FQDN da Web interno (que é o mesmo que o FQDN do servidor)  <br/> • FQDN do servidor  <br/> • FQDN do pool do Skype for Business  <br/> E  <br/> • Conheça URLs simples  <br/> • URL simples de discagem  <br/> • URL simples de administração  <br/> OU  <br/> • Uma entrada curinga para as URLs simples  <br/> |SN=dir01.contoso.com; SAN=dir01.contoso.com; SAN=meet.contoso.com; SAN=meet.fabrikam.com; SAN=dialin.contoso.com; SAN=admin.contoso.com  <br/> Como usar um certificado curinga:  <br/> SN=dir01.contoso.com; SAN=dir01.contoso.com SAN= \* .contoso.com  <br/> |
|Web externa  <br/> |FQDN do servidor  <br/> |Cada um dos seguintes:  <br/> • FQDN da Web Externa  <br/> E  <br/> • Conheça URLs simples por domínio SIP  <br/> • URL simples de discagem  <br/> OU  <br/> • Uma entrada curinga para as URLs simples  <br/> |O FQDN da Web Externa do Diretor deve ser diferente do pool de Front-End ou do Servidor front-end.  <br/> SN=dir01.contoso.com; SAN=directorwebcon01.contoso.com SAN=meet.contoso.com; SAN=meet.fabrikam.com; SAN=dialin.contoso.com  <br/> Como usar um certificado curinga:  <br/> SN=dir01.contoso.com; SAN=directorwebcon01.contoso.com SAN= \* .contoso.com  <br/> |
   
Certificados para Servidor de Mediação Autônomo:
  
|**Certificado**|**Nome do assunto/Nome comum**|**Nome alternativo da entidade**|**Exemplo**|
|:-----|:-----|:-----|:-----|
|Padrão  <br/> |FQDN do pool  <br/> |FQDN do pool  <br/> FQDN do servidor membro do pool  <br/> |SN=medsvr-pool.contoso.net; SAN=medsvr-pool.contoso.net; SAN=medsvr01.contoso.net  <br/> |
   
Certificados para Aparelho de FilialVivível:
  
|**Certificado**|**Nome do assunto/Nome comum**|**Nome alternativo da entidade**|**Exemplo**|
|:-----|:-----|:-----|:-----|
|Padrão  <br/> |FQDN do aplicativo  <br/> |SIP.\<sipdomain\> (você precisa apenas de uma entrada por domínio SIP)  <br/> |SN=sba01.contoso.net; SAN=sip.contoso.com; SAN=sip.fabrikam.com  <br/> |
   
### <a name="certificates-for-your-persistent-chat-server"></a>Certificados para seu Servidor de Chat Persistente

Ao instalar seu Servidor de Chat Persistente, você precisará de um certificado emitido pela mesma CA usada pelos servidores internos do Skype for Business Server 2015. Isso precisa ser feito para cada servidor que executa os Serviços Web de Chat Persistente para Upload/Download de Arquivos. É altamente recomendável que você tenha os certificados necessários antes de iniciar a instalação do Chat Persistente e, se sua AC for externa, ainda mais (essas coisas podem demorar um pouco para serem emitidas).
  
### <a name="certificates-for-external-user-access-edge"></a>Certificados para acesso de usuário externo (Borda)

O Skype for Business Server 2015 oferece suporte ao uso de um único certificado público para interfaces externas de Borda de acesso e webconferência, além do serviço de Autenticação A/V, que é fornecido por meio do(s) Servidor(es) de Borda.  Sua interface interna de Borda normalmente usará um certificado privado emitido por sua AC interna, mas se preferir, também poderá usar um certificado público para isso, se for de uma CA confiável.
  
Seu proxy reverso (RP) também usará um certificado público e criptografa a comunicação de seu RP para os clientes e o RP para servidores internos usando HTTP (ou, mais precisamente, TLS sobre HTTP).
  
### <a name="certificates-for-mobility"></a>Certificados para mobilidade

Se você estiver implantando mobilidade e estiver dando suporte à descoberta automática para clientes móveis, será necessário incluir algumas entradas adicionais de nome alternativo do assunto em seus certificados para oferecer suporte às conexões seguras dos clientes móveis.
  
Quais certificados? Você precisará de nomes SAN para descoberta automática nos certificados aqui:
  
- Director pool
    
- Pool de Front-Ends
    
- Proxy Reverso
    
Listamos os detalhes específicos em cada tabela abaixo.
  
Agora, é aqui que um pouco de pré-planejamento é bom, mas, às vezes, você já implantou o Skype for Business Server 2015 sem a intenção de implantar mobilidade, e isso se resume quando você já tem certificados em seu ambiente. Reemulá-los por meio de uma AC interna normalmente é muito fácil, mas com certificados públicos de uma CA pública, isso pode ser um pouco mais caro.
  
Se for isso que você está vendo e se tiver muitos domínios SIP (o que torna a adição de SANS mais cara), você pode configurar seu proxy reverso para usar HTTP para a solicitação inicial do Serviço de Descoberta Automática, em vez de usar HTTPS (que é a configuração padrão). O tópico Planejamento para Mobilidade tem mais informações sobre isso.
  
Requisitos de certificado do pool de diretores e do pool de front-end:
  
|**Descrição**|**Entrada SAN**|
|:-----|:-----|
|URL interna do serviço descoberta automática  <br/> |SAN=lyncdiscoverinternal.\<sipdomain\>  <br/> |
|URL externa do serviço descoberta automática  <br/> |SAN=lyncdiscover.\<sipdomain\>  <br/> |
   
Como alternativa, você pode usar SAN= \* .\<sipdomain\>
  
Requisitos de certificado de Proxy Reverso (CA Pública:
  
|**Descrição**|**Entrada SAN**|
|:-----|:-----|
|URL externa do serviço descoberta automática  <br/> |SAN=lyncdiscover.\<sipdomain\>  <br/> |
   
Essa SAN precisa ser atribuída ao certificado atribuído ao Ouvinte SSL em seu proxy reverso.
  
> [!NOTE]
> Seu ouvinte de proxy reverso terá SANs para suas URLs de serviços Web externos. Alguns exemplos seriam SAN=skypewebextpool01.contoso.com e dirwebexternal.contoso.com, se você tiver implantado o Diretor(o que é opcional). 
  
## <a name="file-share"></a>Compartilhamento de arquivo
<a name="Fileshare"> </a>

O Skype for Business Server 2015 é capaz de usar o mesmo compartilhamento de arquivos para todo o armazenamento de arquivos. Você precisa ter o seguinte em mente:
  
- Um compartilhamento de arquivos precisa estar em das (direct attached storage) ou em uma rede de área de armazenamento (SAN), e isso inclui o SISTEMA de Arquivos Distribuídos (DFS), bem como uma matriz redundante de discos independentes (RAID) para armazenamentos de arquivos. Para ler mais sobre DFS para Windows Server 2012, confira [esta página DFS.](https://technet.microsoft.com/library/jj127250.aspx)
    
- Recomendamos um cluster compartilhado para o compartilhamento de arquivos. Se você estiver usando um, deverá agrupar o Windows Server 2012 ou o Windows Server 2012 R2. O Windows Server 2008 R2 também é aceitável. Por que o Windows mais recente? As versões mais antigas podem não ter as permissões corretas para habilitar todos os recursos. Você pode usar o Administrador de Cluster para criar os compartilhamentos de arquivos, e isso, como criar compartilhamentos de arquivos em um [artigo de cluster,](https://support.microsoft.com/help/224967/how-to-create-file-shares-on-a-cluster) o ajudará com esses detalhes.
    
> [!CAUTION] 
> Você deve saber que o uso do NAS (armazenamento anexado à rede) como um compartilhamento de arquivos não é suportado, portanto, use uma das opções listadas acima. 
  
