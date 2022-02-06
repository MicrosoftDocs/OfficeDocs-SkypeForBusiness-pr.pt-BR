---
title: Requisitos ambientais Skype for Business Server 2015
ms.reviewer: null
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 2/15/2018
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
  - NOCSH
ms.localizationpriority: medium
ms.collection:
  - IT_Skype16
  - Strat_SB_Admin
ms.custom: null
ms.assetid: 4812c444-2546-48d7-9ca7-b71fce508ed8
description: 'Resumo: Configure seus requisitos de não servidor para Skype for Business Server 2015. Há uma variedade de coisas que você deseja configurar antes de fazer sua implantação, incluindo Active Directory, DNS, Certs e Fileshares.'
---

# <a name="environmental-requirements-for-skype-for-business-server-2015"></a>Requisitos ambientais Skype for Business Server 2015
 
**Resumo:** Configure seus requisitos de não servidor para Skype for Business Server 2015. Há uma variedade de coisas que você deseja configurar antes de fazer sua implantação, incluindo Active Directory, DNS, Certs e Fileshares.
  
O que é um requisito ambiental para Skype for Business Server 2015? Bem, colocamos tudo o que não está diretamente relacionado ao servidor neste tópico, para que você não tenha que fazer o máximo de clique. Se você estiver procurando por Pré-requisitos do Servidor, confira os requisitos do servidor para o documento Skype for Business Server [2015](server-requirements.md). [O Planejamento](../../plan-your-deployment/network-requirements/network-requirements.md) de Rede também é documentado separadamente. Caso contrário, isso é o que temos neste artigo:
  
- [Active Directory](environmental-requirements.md#AD)
  
- [Sistema de Nomes de Domínio (DNS)](environmental-requirements.md#DNS)
  
- [Certificados](environmental-requirements.md#Certs)
  
- [Compartilhamento de Arquivos](environmental-requirements.md#Fileshare)
  
## <a name="active-directory"></a>Active Directory
<a name="AD"> </a>

Embora muitos dados de configuração para servidores e serviços sejam armazenados no armazenamento de Gerenciamento Central do Skype for Business Server 2015, há algumas coisas ainda armazenadas no Active Directory:
  
|**Objetos do Active Directory**|**Tipos de objeto**|
|:-----|:-----|
|Extensões de esquema  <br/> |Extensões do objeto do usuário  <br/> |
||Extensões para o Lync Server 2013 e o Lync Server 2010, para manter a compatibilidade com as versões anteriores com suporte.  <br/> |
|Dados  <br/> |URI SIP do usuário e outras configurações de usuário  <br/> |
||Objetos de contato para aplicativos (como o aplicativo grupo de resposta e o aplicativo Atendedor de Conferência).  <br/> |
||Dados publicados para compatibilidade com compatibilidade.  <br/> |
||Um ponto de controle de serviço (SCP) para o armazenamento de Gerenciamento Central.  <br/> |
||Conta de Autenticação Kerberos (um objeto opcional do computador).  <br/> |
   
### <a name="os-for-domain-controllers"></a>Sistema operacional para controladores de domínio

Então, qual sistema operacional controlador de domínio pode ser usado? Temos a seguinte lista:

- Windows Server 2019 (Você deve ter Skype for Business Server Atualização Cumulativa 5 ou posterior do 2015)
  
- Windows Server 2016
    
- Windows Server 2012 R2
    
- Windows Server 2012
    
- Windows Server 2008 R2
    
- Windows Server 2008
    
Agora, o nível funcional de domínio de qualquer domínio em que você implanta Skype for Business Server 2015 e o nível funcional da floresta de qualquer floresta na qual você implanta Skype for Business Server 2015, deve ser um dos seguintes:

- Windows Server 2019 (Você deve ter Skype for Business Server Atualização Cumulativa 5 ou posterior do 2015)
  
- Windows Server 2016
    
- Windows Server 2012 R2
    
- Windows Server 2012
    
- Windows Server 2008 R2
    
- Windows Server 2008
    
- Windows Server 2003
    
Você pode ter controladores de domínio somente leitura nesses ambientes? Claro, contanto que também haja controladores de domínio writable disponíveis no mesmo site que o Skype for Business Server.
  
Agora, é importante saber que o Skype for Business Server 2015 não dá suporte a domínios com rótulo único. O que eles são? Se você tiver um domínio raiz rotulado contoso.local, tudo bem. Se você tiver um domínio raiz que tenha apenas o nome local, isso não funcionará e não terá suporte como resultado. Um pouco mais sobre isso foi escrito [neste artigo da Base de Dados de Conhecimento](https://support.microsoft.com/kb/300684/en-us).
  
Skype for Business Server 2015 também não dá suporte à renomeação de domínios. Se você realmente precisa fazer isso, precisará desinstalar o Skype for Business Server 2015, renomear o domínio e reinstalar o Skype for Business Server 2015.
  
Por fim, você pode estar lidando com um domínio com um ambiente bloqueado do AD DS, e tudo bem. Temos mais informações sobre como implantar o Skype for Business Server 2015 nesse tipo de ambiente nos documentos de implantação.
  
### <a name="ad-topologies"></a>Topologias do AD

Skype for Business Server topologias com suporte do 2015 são:
  
- Floresta única com domínio único
    
- Floresta única com uma única árvore e vários domínios
    
- Floresta única com várias árvores e namespaces não contíguos
    
- Várias florestas em uma topologia de floresta central
    
- Várias florestas em uma topologia de floresta de recursos
    
- Várias florestas em uma topologia Skype for Business floresta de recursos com Exchange Online
    
- Várias florestas em uma topologia de floresta de recursos com Skype for Business Online e Azure Active Directory Conexão
    
Temos diagramas e descrições para ajudá-lo a determinar qual topologia você tem em seu ambiente ou o que você pode precisar configurar antes de instalar o Skype for Business Server 2015. Para manter isso simples, também estamos incluindo uma chave:
  
![O é uma chave para os ícones usados para Skype for Business diagramas de topologia.](../../media/cc0dbc17-cf81-4b79-bf99-4614cc6828a0.png)
  
#### <a name="single-forest-with-single-domain"></a>Floresta única com domínio único

![Diagrama da floresta única do Active Directory com um único domínio.](../../media/24921a0b-3a3e-4bad-8427-49300e2e3f7a.png)
  
Não fica mais fácil do que isso, é uma floresta de domínio único, essa é uma topologia comum.
  
#### <a name="single-forest-with-a-single-tree-and-multiple-domains"></a>Floresta única com uma única árvore e vários domínios

![Um único diagrama de floresta, árvore única e domínios mutiple.](../../media/63b9f0dd-6bac-4ba9-ae68-8be032d09dcb.png)
  
Este diagrama mostra uma única floresta, novamente, mas também tem um ou mais domínios filho (há três neste exemplo específico). Portanto, o domínio no qual os usuários são criados pode ser diferente do domínio Skype for Business Server 2015 é implantado. Por que se preocupar com isso? É importante lembrar que, quando você implanta um pool de Skype for Business Server front-end, todos os servidores nesse pool precisam estar em um único domínio. Você pode ter administração entre domínios Skype for Business Server suporte de grupos de administradores Windows universais.
  
De volta ao diagrama acima, você pode ver que os usuários de um domínio podem acessar Skype for Business Server pools do mesmo domínio ou de domínios diferentes, mesmo se esses usuários estão em um domínio filho.
  
#### <a name="single-forest-with-multiple-trees-and-disjoint-namespaces"></a>Floresta única com várias árvores e namespaces não contíguos

![Uma única floresta, várias árvores e um diagrama de namespaces diferentes.](../../media/5ede77a1-f5d2-499c-a2c8-d02f3c2f7cd7.png)
  
Pode ser que você tenha uma topologia semelhante a este diagrama, onde você tem uma floresta, mas dentro dessa floresta há vários domínios, com namespaces AD separados. Se esse for o caso, este diagrama é uma boa ilustração, pois temos usuários em três domínios diferentes acessando Skype for Business Server 2015. Linhas sólidas indicam que eles estão acessando um pool de Skype for Business Server em seu próprio domínio, enquanto uma linha tracejada indica que eles estão indo para um pool em uma árvore diferente completamente.
  
Como você pode ver, os usuários no mesmo domínio, na mesma árvore ou mesmo em uma árvore diferente podem acessar pools com êxito.
  
#### <a name="multiple-forests-in-a-central-forest-topology"></a>Várias florestas em uma topologia de floresta central

![Várias florestas em um diagrama de topologia de floresta central.](../../media/fec40746-4254-4c84-86b9-aad4a616ea2f.png)
  
Skype for Business Server 2015 dá suporte a várias florestas configuradas em uma topologia de floresta central. Se você não tiver certeza de que é o que você tem, a floresta central na topologia usará objetos nele para representar usuários nas outras florestas e hospeda contas de usuário para todos os usuários na floresta.
  
Como isso funciona? Bem, um produto de sincronização de diretório (como Forefront Identity Manager ou FIM) gerencia as contas de usuário da sua organização durante toda a sua existência. Quando uma conta é criada ou excluída de uma floresta, essa alteração é sincronizada até o contato correspondente na floresta central.
  
Claramente, se a infraestrutura do AD estiver in-locar a mudança para essa topologia pode não ser fácil, mas se você já estiver lá ou ainda estiver planejando sua infraestrutura de floresta, essa pode ser uma boa opção. Você pode centralizar sua implantação Skype for Business Server 2015 em uma única floresta, enquanto os usuários podem pesquisar, se comunicar e exibir a presença de outros usuários em qualquer floresta. Todas as atualizações de contato do usuário são tratadas automaticamente com software de sincronização.
  
#### <a name="multiple-forests-in-a-skype-for-business-resource-forest-topology"></a>Várias florestas em uma topologia Skype for Business floresta de recursos
<a name="BKMK_multipleforestopology"> </a>

![Várias florestas em um diagrama de topologia de floresta de recursos.](../../media/41efa3b6-d9e6-47df-992b-fefcfc39a80d.png)
  
Uma topologia de floresta de recursos também é suportada; é onde uma floresta é dedicada à execução de seus aplicativos de servidor, como Microsoft Exchange Server e Skype for Business Server 2015. Essas florestas de recursos também hospedam uma representação sincronizada de objetos de usuário ativos, mas nenhuma conta de usuário habilitada para logon. Portanto, a floresta de recursos é um ambiente de serviços compartilhados para outras florestas nas quais os objetos de usuário residem e eles têm uma relação de confiança no nível da floresta com a floresta de recursos.
  
Observe que Exchange Server pode ser implantado na mesma floresta de recursos Skype for Business Server ou em uma floresta diferente.
  
Para implantar o Skype for Business Server 2015 nesse tipo de topologia, você criaria um objeto de usuário desabilitado na floresta de recursos para cada conta de usuário nas florestas do usuário (se o Microsoft Exchange Server já estiver no ambiente, isso pode ser feito para você). Em seguida, você precisará de uma ferramenta de sincronização de diretórios (como Forefront Identity Manager ou FIM) para gerenciar contas de usuário por meio de seu ciclo de vida.
  
#### <a name="multiple-forests-in-a-skype-for-business-resource-forest-topology-with-exchange-online"></a>Várias florestas em uma topologia Skype for Business floresta de recursos com Exchange Online
<a name="BKMK_multipleforestopology"> </a>

Essa topologia é semelhante à topologia descrita em [Várias florestas em uma topologia Skype for Business floresta de recursos](environmental-requirements.md#BKMK_multipleforestopology).
  
Nesta topologia, há uma ou mais florestas de usuários, e Skype for Business Server é implantado em uma floresta de recursos dedicada. Exchange Server pode ser implantado no local na mesma floresta de recursos ou em uma floresta diferente e configurado para híbrido com Exchange Online, ou os serviços de email podem ser fornecidos exclusivamente pelo Exchange Online para as contas locais. Não há nenhum diagrama disponível para essa topologia.
  
#### <a name="multiple-forests-in-a-resource-forest-topology-with-skype-for-business-online-and-azure-active-directory-connect"></a>Várias florestas em uma topologia de floresta de recursos com Skype for Business Online e Azure Active Directory Conexão
<a name="BKMK_multipleforestopology"> </a>

![Mostra duas florestas do AD, uma floresta de usuário e uma floresta de recursos. As duas florestas têm uma relação de confiança. Eles são sincronizados com Microsoft 365 ou Office 365 usando o Azure AD Conexão. Todos os usuários estão habilitados para Skype for Business via Microsoft 365 ou Office 365.](../../media/6d54558d-8786-4ebf-90f6-55ae3fdb5ae7.jpg)
  
Com esse cenário, há várias florestas locais, com uma topologia de floresta de recursos. Há uma relação de confiança total entre as florestas do Active Directory. A Azure Active Directory Conexão é usada para sincronizar contas entre as florestas de usuários locais e Microsoft 365 ou Office 365.
  
 A organização também tem Microsoft 365 ou Office 365 e usa Azure Active Directory Conexão para sincronizar suas contas [](/previous-versions/azure/azure-services/dn832695(v=azure.100)) locais com Microsoft 365 ou Office 365. Os usuários habilitados para Skype for Business estão habilitados por meio de Microsoft 365 ou Office 365 e Skype for Business Online. Skype for Business Server não é implantado no local.
  
A autenticação de login único é fornecida por um farm dos Serviços de Federação do Active Directory localizado na floresta do usuário.
  
Nesse cenário, há suporte para implantar Exchange local, Exchange Online, uma solução de Exchange híbrida ou para não Exchange implantada. (O diagrama mostra apenas Exchange local, mas as outras soluções Exchange também são totalmente suportadas.)
  
#### <a name="multiple-forests-in-a-resource-forest-topology-with-hybrid-skype-for-business"></a>Várias florestas em uma topologia de floresta de recursos com Skype for Business
<a name="BKMK_multipleforestopology"> </a>

Nesse cenário, há uma ou mais florestas de usuários locais, e o Skype for Business é implantado em uma floresta de recursos dedicada e é configurado para o modo híbrido com o Skype for Business Online. Exchange Server pode ser implantado no local na mesma floresta de recursos ou em uma floresta diferente e pode ser configurado para híbrido com Exchange Online. Como alternativa, os serviços de email podem ser fornecidos exclusivamente Exchange Online para as contas locais.
  
Para obter mais informações, [consulte Configure a multi-forest environment for hybrid Skype for Business](../../../SfbHybrid/hybrid/configure-a-multi-forest-environment-for-hybrid.md?bc=%2fSkypeForBusiness%2fbreadcrumb%2ftoc.json&toc=%2fSkypeForBusiness%2ftoc.json).
  
## <a name="domain-name-system-dns"></a>Sistema de Nomes de Domínio (DNS)
<a name="DNS"> </a>

Skype for Business Server 2015 requer DNS, pelos seguintes motivos:
  
- O DNS permite Skype for Business Server 2015 para descobrir servidores ou pools internos, permitindo comunicações de servidor para servidor.
    
- O DNS permite que as máquinas cliente descubram o pool de Front-End ou Edição Standard servidor sendo usado para transações SIP.
    
- Ele associa URLs simples para conferências com os servidores que hospedam essas conferências.
    
- O DNS permite que usuários externos e máquinas cliente se conectem aos Seus Servidores de Borda, ou ao proxy reverso HTTP, para mensagens instantâneas (IM) ou conferência.
    
- Ele permite que os dispositivos de comunicações unificadas (UC) que não estão conectados descubram o pool de Front-End ou o servidor Edição Standard que está executando o serviço Web de Atualização de Dispositivo para obter atualizações e enviar logs.
    
- O uso do DNS permite que os clientes móveis descubram automaticamente recursos de serviços Web sem exigir que os usuários insiram manualmente URLs em suas configurações de dispositivo.
    
- E é usado no balanceamento de carga DNS.
    
É importante observar que o Skype for Business Server 2015 não dá suporte a IDNs (nomes de domínio internacionalizados).
  
E é extremamente importante lembrar que qualquer nome no DNS seja idêntico ao nome do computador configurado em qualquer servidor que está sendo usado pelo Skype for Business Server 2015. Especificamente, não podemos ter nomes curtos no ambiente e devem ter FQDNs para Construtor de Topologias.
  
Isso parece lógico para qualquer computador já ingressado em um domínio, mas se você tiver um Servidor de Borda que não está ingressado no seu domínio, ele pode ter um padrão de um nome curto, sem sufixo de domínio. Certifique-se de que esse não seja o caso, seja no DNS ou no Servidor de Borda, ou em qualquer servidor ou pool Skype for Business Server 2015, para esse assunto.
  
E definitivamente não use caracteres Unicode ou sublinhados. Os caracteres padrão (que são A-Z, a-z, 0-9 e hífens) são os que serão suportados por DNS externo e autoridades públicas de certificado (você precisará atribuir FQDNs ao SN no certificado, não se esqueça), portanto, você se poupará de muita dor se tiver esse nome em mente.
  
Para saber mais sobre os requisitos de DNS para Rede, confira a seção [Rede](../../plan-your-deployment/network-requirements/network-requirements.md) da nossa documentação de Planejamento.
  
## <a name="certificates"></a>Certificados
<a name="Certs"> </a>

Uma das coisas mais importantes que você pode fazer antes de implantar é garantir que você tenha seus certificados em ordem. Skype for Business Server 2015 precisa de uma infraestrutura de chave pública (PKI) para conexões de segurança de camada de transporte (TLS) e MTLS (mutual transport layer security). Basicamente, para se comunicar com segurança de forma padronizada, Skype for Business Server usa certificados emitidos pelas Autoridades de Certificação (CAs).
  
Estas são algumas das coisas que o Skype for Business Server 2015 usa certificados para:
  
- Conexões TLS entre clientes e servidores
    
- Conexões MTLS entre servidores
    
- Federação usando a descoberta automática de parceiros no DNS
    
- Acesso de usuários remotos a IM (mensagens instantâneas)
    
- Acesso do usuário externo a sessões de áudio/vídeo (AV), compartilhamento de aplicativos e conferência
    
- Conversando com aplicativos Web e Outlook Web Access (OWA)
    
Portanto, o planejamento de certificados é necessário. Agora, vamos ver uma lista de algumas das coisas que você precisa ter em mente ao solicitar certificados:
  
- Todos os certificados de servidor devem oferecer suporte à autorização de servidor (EKU de servidor).
    
- Todos os certificados de servidor devem conter um CDP (Ponto de Distribuição de CRL).
    
- Todos os certificados devem ser assinados usando um algoritmo de assinatura com suporte do sistema operacional. Skype for Business Server 2015 oferece suporte ao pacote SHA-1 e SHA-2 de tamanhos digest (224, 256, 384 e 512 bits) e atende ou excede os requisitos do sistema operacional.
    
- O registro automático é suportado para servidores internos que executam Skype for Business Server 2015.
    
- O registro automático não é suportado para servidores de borda Skype for Business Server 2015.
    
- Quando você envia uma solicitação de certificado baseado em web para uma AC Windows Server 2003, você deve submete-la de um computador que esteja executando Windows Server 2003 com SP2 ou Windows XP.
    
> [!NOTE]
> Embora o KB922706 oferece suporte para resolver problemas com o registro de certificados Web em um registro do Windows Server 2003 Certificate Services, ele não permite usar o Windows Server 2008, o Windows Vista ou o Windows 7 para solicitar um certificado de uma CA do Windows Server 2003. 
  
> [!NOTE]
> O uso do algoritmo de assinatura RSASSA-PSS não é compatível e pode levar a erros em problemas de logon e encaminhamento de chamada, entre outros problemas. 

> [!NOTE]
> Skype for Business Server 2015 não dá suporte a certificados CNG.
  
- Há suporte para comprimentos de chave de criptografia 1024, 2048 e 4096. Recomenda-se comprimentos principais de 2048 e maiores.
    
- O algoritmo digest padrão ou assinatura de hash é RSA. Os ECDH_P256, ECDH_P384 e ECDH_P521 algoritmos também são suportados.
    
Portanto, isso é muito sobre o que pensar e, definitivamente, há uma variedade de níveis de conforto com a solicitação de certificados de uma AC. Vamos dar mais orientações abaixo para tornar seu planejamento o mais indolor possível.
  
### <a name="certificates-for-your-internal-servers"></a>Certificados para seus servidores internos

Você precisará de certificados para a maioria dos seus servidores internos e, provavelmente, você os obterá de uma AC interna (que é uma localizada em seu domínio). Se quiser, você pode solicitar esses certificados de uma AC externa (uma localizada na Internet). Se você estiver se perguntando para qual ac pública você deve ir, confira a lista de parceiros de [certificados de Comunicações](../../../SfbPartnerCertification/certification/services-ssl.md) Unificadas.
  
Você também precisará de certificados quando o Skype for Business Server 2015 se comunicar com outros aplicativos e servidores, como Microsoft Exchange Server. Isso, obviamente, precisará ser um certificado que esses outros aplicativos e servidores podem usar de forma suportada. Skype for Business Server 2015 e outros produtos Microsoft suportam o protocolo OAuth (Autorização Aberta) para autenticação e autorização de servidor para servidor. Se você estiver interessado nisso, temos um artigo de planejamento adicional para OAuth e Skype for Business Server 2015.
  
Skype for Business Server 2015 também inclui suporte para certificados assinados (sem a necessidade) usando a função hash criptográfico SHA-256. Para dar suporte ao acesso externo usando SHA-256, o certificado externo precisa ser emitido por uma AC pública usando SHA-256.
  
Para tentar manter as coisas simples, colocamos os requisitos de certificado para servidores Edição Standard, pools front-end e outras funções, nas tabelas a seguir, com o contoso.com fictício sendo usado para exemplos (você provavelmente estará usando algo mais para seu ambiente). Todos eles são certificados de servidor Web padrão, com chaves privadas que não são exportáveis. Algumas coisas adicionais a observar:
  
- O uso de chave aprimorada do servidor (EKU) é configurado automaticamente quando você usa o assistente de certificado para solicitar certificados.
    
- Cada nome amigável de certificado deve ser exclusivo no armazenamento do computador.
    
- De acordo com os nomes de exemplo abaixo, se você configurou sipinternal.contoso.com ou sipexternal.contoso.com em seu DNS, eles precisarão ser adicionados ao SAN (Subject Alternative Name) do certificado.
    
Certificados para servidores Edição Standard:
  
|**Certificado**|**Nome do assunto/Nome comum**|**Nome alternativo da entidade**|**Exemplo**|**Comments**|
|:-----|:-----|:-----|:-----|:-----|
|Padrão  <br/> |FQDN do pool  <br/> |FQDN do pool e FQDN do servidor  <br/> Se você tiver vários domínios SIP e tiver habilitado a configuração automática do cliente, o assistente de certificados detectará e adicionará os FQDNs de cada domínio SIP aceito.  <br/> Se esse pool é o servidor de logon automático para clientes, e a combinação estrita do Sistema de Nome de Domínio (DNS) é exigida na política do grupo, também é preciso de entradas para o sip.sipdomain (para cada domínio de SIP que você tiver).  <br/> |SN=se01.contoso.com; SAN=se01.contoso.com  <br/> Se esse pool é o servidor de logon automático para clientes, e se a combinação estrita de DNS for exigida na política do grupo, também serão precisos: SAN=sip.contoso.com; SAN=sip.fabrikam.com  <br/> |No servidor Standard Edition, o servidor FQDN é o mesmo que o pool FQDN.  <br/> O assistente detecta todos os domínios SIP especificados durante a instalação e os adiciona automaticamente como nomes alternativos de assunto.  <br/> Você também pode usar esse certificado para Autenticação de Servidor para Servidor.  <br/> |
|Web interna  <br/> |FQDN do servidor  <br/> |Cada um dos seguintes:  <br/> • FQDN da Web interna (que é o mesmo que o FQDN do servidor)  <br/> E  <br/> • Conheça URLs simples  <br/> • URL simples discado  <br/> • URL simples do administrador  <br/> OU  <br/> • Uma entrada curinga para as URLs simples  <br/> |SN=se01.contoso.com; SAN=se01.contoso.com; SAN=meet.contoso.com; SAN=meet.fabrikam.com; SAN=dialin.contoso.com; SAN=admin.contoso.com  <br/> Como usar um certificado curinga:  <br/> SN=se01.contoso.com; SAN=se01.contoso.com; SAN=\*.contoso.com  <br/> |Não é possível substituir o FQDN Da Web Interno no Construtor de Topologias.  <br/> Se você tiver várias URLs simples de Meet, será preciso incluir todas elas como SANs.  <br/> As entradas curinga são suportadas pelas entradas de URL simples.  <br/> |
|Web externa  <br/> |FQDN do servidor  <br/> |Cada um dos seguintes:  <br/> • FQDN web externo  <br/> E  <br/> • URL simples discado  <br/> • Atender a URLs simples por domínio SIP  <br/> OU  <br/> • Uma entrada curinga para as URLs simples  <br/> |SN=se01.contoso.com; SAN=webcon01.contoso.com; SAN=meet.contoso.com; SAN=meet.fabrikam.com; SAN=dialin.contoso.com  <br/> Como usar um certificado coringa:  <br/> SN=se01.contoso.com; SAN=webcon01.contoso.com; SAN=\*.contoso.com  <br/> |Se você tiver várias URLs simples de Meet, você terá que incluir todas elas como nomes alternativos de assunto.  <br/> As entradas curinga são suportadas pelas entradas de URL simples.  <br/> |
   
Certificados para servidores front-end em um pool Edição Enterprise front-end:
  
|**Certificado**|**Nome do assunto/Nome comum**|**Nome alternativo da entidade**|**Exemplo**|**Comments**|
|:-----|:-----|:-----|:-----|:-----|
|Padrão  <br/> |FQDN do pool  <br/> |FQDN do pool e FQDN do servidor  <br/> Se você tiver vários domínios SIP e tiver habilitado a configuração automática do cliente, o assistente de certificados detectará e adicionará os FQDNs de cada domínio SIP aceito.  <br/> Se esse pool é o servidor de logon automático para clientes, e a combinação estrita do Sistema de Nome de Domínio (DNS) é exigida na política do grupo, também é preciso de entradas para o sip.sipdomain (para cada domínio de SIP que você tiver).  <br/> |SN=eepool.contoso.com; SAN=eepool.contoso.com; SAN=ee01.contoso.com  <br/> Se esse pool é o servidor de logon automático para clientes, e se a combinação estrita de DNS for exigida na política do grupo, também serão precisos: SAN=sip.contoso.com; SAN=sip.fabrikam.com  <br/> |O assistente detecta quaisquer domínios SIP especificados durante a instalação e os adiciona automaticamente ao nome alternativo para a entidade.  <br/> Você também pode usar esse certificado para Autenticação de Servidor para Servidor.  <br/> |
|Web interna  <br/> |FQDN do pool  <br/> |Cada um dos seguintes:  <br/> • FQDN da Web interna (que NÃO é o mesmo que o FQDN do servidor)  <br/> • FQDN do servidor  <br/> • Skype for Business FQDN do pool  <br/> E  <br/> • Conheça URLs simples  <br/> • URL simples discado  <br/> • URL simples do administrador  <br/> OU  <br/> • Uma entrada curinga para as URLs simples  <br/> |SN=ee01.contoso.com; SAN=ee01.contoso.com; SAN=meet.contoso.com; SAN=meet.fabrikam.com; SAN=dialin.contoso.com; SAN=admin.contoso.com  <br/> Como usar um certificado curinga:  <br/> SN=ee01.contoso.com; SAN=ee01.contoso.com; SAN=\*.contoso.com  <br/> |Se você tiver várias URLs simples de Meet, você terá que incluir todas elas como nomes alternativos de assunto.  <br/> As entradas curinga são suportadas pelas entradas de URL simples.  <br/> |
|Web externa  <br/> |FQDN do pool  <br/> |Cada um dos seguintes:  <br/> • FQDN web externo  <br/> E  <br/> • URL simples discado  <br/> • URL simples do administrador  <br/> OU  <br/> • Uma entrada curinga para as URLs simples  <br/> |SN=ee01.contoso.com; SAN=webcon01.contoso.com; SAN=meet.contoso.com; SAN=meet.fabrikam.com; SAN=dialin.contoso.com  <br/> Como usar um certificado curinga:  <br/> SN=ee01.contoso.com; SAN=webcon01.contoso.com; SAN=\*.contoso.com  <br/> |Se você tiver várias URLs simples de Meet, você terá que incluir todas elas como nomes alternativos de assunto.  <br/> As entradas curinga são suportadas pelas entradas de URL simples.  <br/> |
   
Certificados para o Diretor:
  
|**Certificado**|**Nome do assunto/Nome comum**|**Nome alternativo da entidade**|**Exemplo**|
|:-----|:-----|:-----|:-----|
|Padrão  <br/> |Director pool  <br/> |FQDN do Diretor, FQDN do pool de diretores.  <br/> Se esse pool for o servidor de logon automático para clientes e a correspondência DNS estrita for necessária na política de grupo, você também precisará de entradas para sip.sipdomain (para cada domínio SIP que você tem).  <br/> |pool.contoso.com; SAN=dir01.contoso.com  <br/> Se esse pool de Diretor for o servidor de logon automático para clientes, e se a combinação estrita de DNS for exigida na política do grupo, também serão precisos: SAN=sip.contoso.com; SAN=sip.fabrikam.com  <br/> |
|Web interna  <br/> |FQDN do servidor  <br/> |Cada um dos seguintes:  <br/> • FQDN da Web interna (que é o mesmo que o FQDN do servidor)  <br/> • FQDN do servidor  <br/> • Skype for Business FQDN do pool  <br/> E  <br/> • Conheça URLs simples  <br/> • URL simples discado  <br/> • URL simples do administrador  <br/> OU  <br/> • Uma entrada curinga para as URLs simples  <br/> |SN=dir01.contoso.com; SAN=dir01.contoso.com; SAN=meet.contoso.com; SAN=meet.fabrikam.com; SAN=dialin.contoso.com; SAN=admin.contoso.com  <br/> Como usar um certificado curinga:  <br/> SN=dir01.contoso.com; SAN=dir01.contoso.com SAN=\*.contoso.com  <br/> |
|Web externa  <br/> |FQDN do servidor  <br/> |Cada um dos seguintes:  <br/> • FQDN web externo  <br/> E  <br/> • Atender a URLs simples por domínio SIP  <br/> • URL simples discado  <br/> OU  <br/> • Uma entrada curinga para as URLs simples  <br/> |O FQDN da Web externo do Diretor deve ser diferente do pool de Front-End ou do Servidor Front-End.  <br/> SN=dir01.contoso.com; SAN=directorwebcon01.contoso.com SAN=meet.contoso.com; SAN=meet.fabrikam.com; SAN=dialin.contoso.com  <br/> Como usar um certificado curinga:  <br/> SN=dir01.contoso.com; SAN=directorwebcon01.contoso.com SAN=\*.contoso.com  <br/> |
   
Certificados para Servidor de Mediação Autônomo:
  
|**Certificado**|**Nome do assunto/Nome comum**|**Nome alternativo da entidade**|**Exemplo**|
|:-----|:-----|:-----|:-----|
|Padrão  <br/> |FQDN do pool  <br/> |FQDN do pool  <br/> FQDN do servidor membro do pool  <br/> |SN=medsvr-pool.contoso.net; SAN=medsvr-pool.contoso.net; SAN=medsvr01.contoso.net  <br/> |
   
Certificados para Aparelho de Filial Desavivável:
  
|**Certificado**|**Nome do assunto/Nome comum**|**Nome alternativo da entidade**|**Exemplo**|
|:-----|:-----|:-----|:-----|
|Padrão  <br/> |FQDN do aplicativo  <br/> |SIP.\<sipdomain\> (você precisa de apenas uma entrada por domínio SIP)  <br/> |SN=sba01.contoso.net; SAN=sip.contoso.com; SAN=sip.fabrikam.com  <br/> |
   
### <a name="certificates-for-your-persistent-chat-server"></a>Certificados para seu Servidor de Chat Persistente

Ao instalar o Servidor de Chat Persistente, você precisará de um certificado emitido pela mesma AC usada pelos servidores internos Skype for Business Server 2015. Isso precisa ser feito para cada servidor que executa os Serviços Web de Chat Persistente para Arquivos Upload/Download. É altamente recomendável que você tenha os certificados necessários antes de iniciar a instalação do Chat Persistente e se sua AC for externa, ainda mais (essas coisas podem demorar um pouco para serem emitidas).
  
### <a name="certificates-for-external-user-access-edge"></a>Certificados para acesso de usuário externo (Borda)

Skype for Business Server 2015 oferece suporte ao uso de um único certificado público  para interfaces externas de Borda de Acesso e Webconferência, além do serviço de Autenticação A/V, que é todo fornecido por meio dos Servidores de Borda. Sua interface interna de Borda normalmente usará um certificado privado emitido pela ac interna, mas, se preferir, você também poderá usar um certificado público para isso, se for de uma AC confiável.
  
Seu proxy reverso (RP) também usará um certificado público e criptografa a comunicação de seu RP para clientes e o RP para servidores internos usando HTTP (ou, mais precisamente, TLS sobre HTTP).
  
### <a name="certificates-for-mobility"></a>Certificados de mobilidade

Se você estiver implantando mobilidade e estiver dando suporte à descoberta automática para clientes móveis, você precisará incluir algumas entradas adicionais de nomes alternativos de assunto em seus certificados para dar suporte às conexões seguras dos clientes móveis.
  
Quais certificados? Você precisará de nomes SAN para descoberta automática nos certificados aqui:
  
- Director pool
    
- Pool de Front-Ends
    
- Proxy Reverso
    
Listamos os detalhes em cada tabela abaixo.
  
Agora, é aqui que um pouco de pré-planejamento é bom, mas às vezes você implantou o Skype for Business Server 2015 sem a intenção de implantar a mobilidade, e isso acontece quando você já tem certificados em seu ambiente. Reemissão por meio de uma AC interna normalmente é muito fácil, mas com certificados públicos de uma AC pública, isso pode ser um pouco mais caro.
  
Se for isso que você está vendo e se você tiver muitos domínios SIP (o que torna a adição de SANS mais cara), você pode configurar seu proxy reverso para usar HTTP para a solicitação inicial do Serviço de Descoberta Automática, em vez de usar HTTPS (que é a configuração padrão). O tópico Planejamento para Mobilidade tem mais informações sobre isso.
  
Requisitos de certificado de pool de diretores e de pool de front-end:
  
|**Descrição**|**Entrada SAN**|
|:-----|:-----|
|URL do serviço de Descoberta Automática Interna  <br/> |SAN=lyncdiscoverinternal.\<sipdomain\>  <br/> |
|URL do serviço de Descoberta Automática Externa  <br/> |SAN=lyncdiscover.\<sipdomain\>  <br/> |
   
Como alternativa, você pode usar SAN=\*.\<sipdomain\>
  
Requisitos de certificado de Proxy Reverso (CA Pública):
  
|**Descrição**|**Entrada SAN**|
|:-----|:-----|
|URL do serviço de Descoberta Automática Externa  <br/> |SAN=lyncdiscover.\<sipdomain\>  <br/> |
   
Essa SAN precisa ser atribuída ao certificado atribuído ao Ouvinte SSL em seu proxy reverso.
  
> [!NOTE]
> Seu ouvinte de proxy reverso terá SANs para suas URL(s) de Serviços Web externos. Alguns exemplos seriam SAN=skypewebextpool01.contoso.com e dirwebexternal.contoso.com, se você tiver implantado o Diretor ( o que é opcional). 
  
## <a name="file-share"></a>Compartilhamento de arquivo
<a name="Fileshare"> </a>

Skype for Business Server 2015 é capaz de usar o mesmo compartilhamento de arquivos para todo o armazenamento de arquivos. Você precisa ter o seguinte em mente:
  
- Um compartilhamento de arquivos precisa estar no DAS (armazenamento anexado direto) ou em uma san (rede de área de armazenamento), e isso inclui o DFS (Sistema de Arquivos Distribuídos), bem como uma matriz redundante de discos independentes (RAID) para armazenamentos de arquivos. Para saber mais sobre o DFS para Windows Server 2012, confira [esta página DFS](/previous-versions/windows/it-pro/windows-server-2012-R2-and-2012/jj127250(v=ws.11)).
    
- Recomendamos um cluster compartilhado para o compartilhamento de arquivos. Se você estiver usando um, deverá agrupar Windows Server 2012 ou Windows Server 2012 R2. Windows Server 2008 R2 também é aceitável. Por que a última Windows? As versões mais antigas podem não ter as permissões corretas para habilitar todos os recursos. Você pode usar o Administrador de Cluster para criar os compartilhamentos de arquivos e isso Como criar compartilhamentos de arquivo em um [artigo de cluster](https://support.microsoft.com/help/224967/how-to-create-file-shares-on-a-cluster) ajudará você com esses detalhes.
    
> [!CAUTION] 
> Você deve saber que o uso do NAS (armazenamento anexado à rede) como compartilhamento de arquivos não é suportado, portanto, use uma das opções listadas acima. 
