---
title: Requisitos de ambiente para o Skype for Business Server 2015
ms.reviewer: ''
ms.author: heidip
author: microsoftheidi
manager: serdars
ms.date: 2/15/2018
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 4812c444-2546-48d7-9ca7-b71fce508ed8
description: 'Resumo: Configure seus requisitos de não-servidor para Skype para Business Server 2015. Há uma variedade de coisas que você vai querer configurado antes de sua implantação, incluindo o Active Directory, DNS, certificados e compartilhamentos de arquivos.'
ms.openlocfilehash: a75301a6f6f26ac933841ead0192d707d0647897
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/27/2019
ms.locfileid: "30887134"
---
# <a name="environmental-requirements-for-skype-for-business-server-2015"></a>Requisitos de ambiente para o Skype for Business Server 2015
 
**Resumo:** Configure seus requisitos de não-servidor para Skype para Business Server 2015. Há uma variedade de coisas que você vai querer configurado antes de sua implantação, incluindo o Active Directory, DNS, certificados e compartilhamentos de arquivos.
  
O que é um requisito de ambiente para Skype para Business Server 2015? Bem, nós agrupamos tudo o que não é diretamente relacionado neste tópico, portanto você não precisa fazer como muito clicando em ao redor do servidor. Se você estiver procurando por pré-requisitos de servidor, você pode visitar o doc. [requisitos de servidor para Skype para Business Server 2015](server-requirements.md) [Networking planejamento](../../plan-your-deployment/network-requirements/network-requirements.md) também está documentado separadamente. Caso contrário, este é o que nós temos neste artigo:
  
- [Active Directory](environmental-requirements.md#AD)
  
- [DNS (Sistema de Nomes de Domínio)](environmental-requirements.md#DNS)
  
- [Certificados](environmental-requirements.md#Certs)
  
- [Compartilhamento de arquivos](environmental-requirements.md#Fileshare)
  
## <a name="active-directory"></a>Active Directory
<a name="AD"> </a>

Enquanto muitos dados de configuração para servidores e serviços é armazenado no Skype para repositório de gerenciamento Central do Business Server 2015, há algumas coisas que ainda são armazenadas no Active Directory:
  
|**Objetos do Active Directory**|**Tipos de objeto**|
|:-----|:-----|
|Extensões de esquema  <br/> |Extensões de objetos de usuário  <br/> |
||Extensões para o Lync Server 2013 e Lync Server 2010 manter a compatibilidade com versões anteriores com anterior versões com suporte.  <br/> |
|Dados  <br/> |URI do SIP do usuário e outras configurações de usuário  <br/> |
||Objetos de contato para aplicativos (como o aplicativo grupo de resposta e aplicativo Atendedor de conferência).  <br/> |
||Dados publicados para compatibilidade com versões anteriores.  <br/> |
||O ponto de um controle de serviço (SCP) para o repositório de gerenciamento Central.  <br/> |
||Conta de autenticação Kerberos (um objeto de computador opcional).  <br/> |
   
### <a name="os-for-domain-controllers"></a>OS para controladores de domínio

Portanto, qual OS para controladores de domínio pode ser usada? Temos a seguinte lista:
  
- Windows Server 2016
    
- Windows Server 2012 R2
    
- Windows Server 2012
    
- Windows Server 2008 R2
    
- Windows Server 2008
    
Agora, o nível funcional do domínio de qualquer domínio em que você implantar o Skype para 2015 do servidor de negócios em e o nível funcional de floresta de qualquer floresta que você implanta o Skype para o servidor de negócios 2015 into, precisam ser uma das seguintes opções:
  
- Windows Server 2016
    
- Windows Server 2012 R2
    
- Windows Server 2012
    
- Windows Server 2008 R2
    
- Windows Server 2008
    
- Windows Server 2003
    
É possível ter controladores de domínio somente leitura nesses ambientes? Sim, desde que também haja controladores de domínio graváveis disponíveis.
  
Agora, é importante saber que Skype para Business Server 2015 não dá suporte a domínios com rótulo único. O que são esses domínios? Se você tiver um domínio raiz rotulado Contoso, que vai ser tudo bem. Se você tiver um domínio raiz chamado apenas local, que não vai funcionar, e não é suportado como resultado. Um pouco mais sobre isso foi escrito [neste artigo da Base de dados de Conhecimento](https://support.microsoft.com/kb/300684/en-us).
  
Skype para Business Server 2015 também não tem suporte para renomeação de domínios. Se você realmente tem que fazer, em seguida, você vai precisa desinstalar Skype para negócios 2015 do servidor, faça a renomeação de domínio e reinstalar Skype para Business Server 2015.
  
Finalmente, talvez você esteja lidando com um domínio com um ambiente do AD DS bloqueados, e que está tudo bem. Temos obter mais informações sobre como implantar o Skype para Business Server 2015 para esse tipo de ambiente em que os documentos de implantação.
  
### <a name="ad-topologies"></a>Topologias do AD

Skype para as topologias suportadas do Business Server 2015 são:
  
- Floresta única com domínio único
    
- Floresta única com uma única árvore e vários domínios
    
- Floresta única com várias árvores e namespaces não contíguos
    
- Várias florestas em uma topologia de floresta central
    
- Várias florestas em uma topologia de floresta de recursos
    
- Várias florestas em uma topologia de floresta de recursos do Skype for Business com o Exchange Online
    
- Várias florestas em uma topologia de floresta de recursos com Skype for Business Online e Azure Active Directory Connect
    
Temos diagramas e descrições para ajudá-lo a determinar qual topologia que você tem no seu ambiente, ou o que você pode precisar configurar antes da instalação do Skype para Business Server 2015. Para manter simples, estamos incluindo também uma chave:
  
![O é uma chave aos ícones usado para Skype para diagramas da topologia de negócios](../../media/cc0dbc17-cf81-4b79-bf99-4614cc6828a0.png)
  
#### <a name="single-forest-with-single-domain"></a>Floresta única com domínio único

![Diagrama de única floresta do Active Directory com um único domínio](../../media/24921a0b-3a3e-4bad-8427-49300e2e3f7a.png)
  
Nada é mais fácil do que isso, é uma floresta de domínio único, isso é uma topologia comum.
  
#### <a name="single-forest-with-a-single-tree-and-multiple-domains"></a>Floresta única com uma única árvore e vários domínios

![Uma única floresta, a única árvore e o diagrama de domínios de texto com várias](../../media/63b9f0dd-6bac-4ba9-ae68-8be032d09dcb.png)
  
Esse diagrama mostra uma floresta única, mas ela também tem um ou mais domínios filho (há três deles neste exemplo específico). Portanto o domínio em que os usuários são criados no pode ser diferente do domínio Skype para Business Server 2015 é implantado. Por que isso é relevante? É importante lembrar que, quando você implanta um Skype para pool de Front End do servidor de negócios, todos os servidores desse pool precisam estar em um único domínio. Você pode ter administração de domínio cruzado via Skype para suporte do servidor de negócios dos grupos de universal de administradores do Windows.
  
Voltar ao diagrama acima, você pode ver que os usuários de um domínio são capazes de acessar Skype para pools de servidor de negócios do mesmo domínio ou de domínios diferentes, mesmo se os usuários estiverem em um domínio filho.
  
#### <a name="single-forest-with-multiple-trees-and-disjoint-namespaces"></a>Floresta única com várias árvores e namespaces não contíguos

![Uma única floresta, várias árvores e namespaces não contíguo diagrama](../../media/5ede77a1-f5d2-499c-a2c8-d02f3c2f7cd7.png)
  
Pode ser que você acaba de criar uma topologia semelhante a este diagrama, onde você tem uma floresta, mas dentro dessa floresta estão vários domínios, com os namespaces separados do AD. Se for esse o caso, este diagrama 's uma BOM ilustração, como temos usuários em três domínios diferentes accessing Skype para Business Server 2015. Linhas sólidas indicam que eles estiver acessando um Skype para pool de servidores de negócios em seu próprio domínio, enquanto uma linha tracejada indica que irão para um pool em uma árvore diferente todo.
  
Como você pode ver, usuários no mesmo domínio, na mesma árvore ou mesmo em uma árvore diferente conseguem acessar os pools com sucesso.
  
#### <a name="multiple-forests-in-a-central-forest-topology"></a>Várias florestas em uma topologia de floresta central

![Várias florestas em um diagrama de topologia de floresta central](../../media/fec40746-4254-4c84-86b9-aad4a616ea2f.png)
  
Skype para Business Server 2015 dá suporte a várias florestas configuradas em uma topologia de floresta central. Se você não tiver certeza de que é o que você tem, a floresta central na topologia usa objetos para representar usuários nas outras florestas e contas de usuário de hosts para todos os usuários da floresta.
  
Como isso funciona? Bem, um produto de sincronização de diretório (por exemplo, Forefront Identity Manager ou FIM) gerencia as contas de usuário da sua organização em toda sua existência. Quando uma conta é criada ou excluída de uma floresta, essa mudança é sincronizada até o contato correspondente na floresta central.
  
Sem dúvida, se sua infraestrutura do AD está in-loco a movimentação para esta topologia pode não ser fácil, mas se você já existe, ou ainda planejamento sua infra-estrutura de floresta, isso pode ser uma boa opção. Você pode centralizar seu Skype para implantação Business Server 2015 em uma única floresta, enquanto os usuários podem pesquisar, se comunicar e visualizar a presença de outros usuários em qualquer floresta. Todas as atualizações de contato são feitas automaticamente com o software de sincronização.
  
#### <a name="multiple-forests-in-a-skype-for-business-resource-forest-topology"></a>Várias florestas em uma topologia de floresta de recursos do Skype for Business
<a name="BKMK_multipleforestopology"> </a>

![Várias florestas em um diagrama de topologia de floresta de recursos](../../media/41efa3b6-d9e6-47df-992b-fefcfc39a80d.png)
  
Também há suporte para uma topologia de floresta de recursos; é onde uma floresta é dedicada à execução de aplicativos de servidor, como o Microsoft Exchange Server e do Skype para Business Server 2015. Essas florestas de recursos também hospedam uma representação sincronizada de objetos de usuário ativo, mas não contas de usuário habilitadas para logon. Portanto, a floresta de recursos é um ambiente de serviços compartilhados para outras florestas nas quais os objetos de usuários residem, e que têm uma relação de confiança no nível de floresta com a floresta de recursos.
  
Observe que o Exchange Server pode ser implantado na floresta de recursos como Skype para Business Server ou em uma floresta diferente.
  
Para implantar o Skype para o servidor de negócios 2015 nesse tipo de topologia, você criará um objeto de usuário desabilitado na floresta de recursos para cada conta de usuário nas florestas de usuário (se Microsoft Exchange Server já estiver no ambiente, isso pode ser feito para você). Em seguida, você precisará uma ferramenta de sincronização de diretórios (como o Forefront Identity Manager ou FIM) para gerenciar contas de usuário por meio do seu ciclo de vida.
  
#### <a name="multiple-forests-in-a-skype-for-business-resource-forest-topology-with-exchange-online"></a>Várias florestas em uma topologia de floresta de recursos do Skype for Business com o Exchange Online
<a name="BKMK_multipleforestopology"> </a>

Esta topologia é similar à topologia descrita em [Várias florestas em uma topologia de floresta de recursos do Skype for Business](environmental-requirements.md#BKMK_multipleforestopology).
  
Nessa topologia, há uma ou mais florestas de usuário e Skype para Business Server é implantado em uma floresta de recurso dedicado. Exchange Server podem ser implantados no local na mesma floresta do recurso ou uma floresta diferente e configurado para o híbrido com o Exchange Online ou serviços de email podem ser fornecidos exclusivamente pelo Exchange Online para as contas locais. Não há um diagrama disponível para esta topologia.
  
#### <a name="multiple-forests-in-a-resource-forest-topology-with-skype-for-business-online-and-azure-active-directory-connect"></a>Várias florestas em uma topologia de floresta de recursos com Skype for Business Online e Azure Active Directory Connect
<a name="BKMK_multipleforestopology"> </a>

![Mostra duas florestas do AD, a floresta de um usuário e a floresta de um recurso. As duas florestas têm uma relação de confiança. Eles são sincronizados com o Office 365 usando Connect do Azure AD. Todos os usuários estão habilitados para Skype para negócios por meio do Office 365.](../../media/6d54558d-8786-4ebf-90f6-55ae3fdb5ae7.jpg)
  
Neste cenário há várias florestas locais, com uma topologia de floresta de recursos. Há um relacionamento de total confiança entre as florestas do Active Directory. A ferramenta Azure Active Directory Connect é usada para sincronizar contas entre as florestas de usuários locais e o Office 365.
  
 A organização também tem o Office 365 e usa o [Azure Active Directory Connect](https://go.microsoft.com/fwlink/p/?LinkId=614836) para sincronizar suas contas no local com o Office 365. Os usuários habilitados para o Skype para negócios estão habilitados por meio do Office 365 e Skype para Business Online. Skype para Business Server não é implantados no local.
  
Autenticação de logon única é fornecida por um farm de serviços de Federação do Active Directory localizado na floresta de usuário.
  
Neste cenário, ele é suportado para implantar o Exchange local, o Exchange Online, uma solução híbrida do Exchange, ou não tiver implantado em todos os de câmbio. O diagrama mostra somente o Exchange no Local, mas as outras soluções do Exchange são totalmente aceitas.
  
#### <a name="multiple-forests-in-a-resource-forest-topology-with-hybrid-skype-for-business"></a>Várias florestas em uma topologia de floresta de recursos com o Skype for Business híbrido 
<a name="BKMK_multipleforestopology"> </a>

Neste cenário, há um ou mais locais florestas de usuários e Skype para negócios é implantado em uma floresta de recurso dedicado e está configurado para modo híbrido com Skype para negócios Online. Exchange Server podem ser implantados no local na mesma floresta do recurso ou uma floresta diferente e pode ser configurado para o híbrido com o Exchange Online. Como alternativa, os serviços de email podem ser fornecidos exclusivamente pelo Exchange Online para as contas locais.
  
Para obter mais informações, consulte [Configure um ambiente de várias floresta para o híbrido Skype para negócios](../../skype-for-business-hybrid-solutions/deploy-hybrid-connectivity/configure-a-multi-forest-environment-for-hybrid.md).
  
## <a name="domain-name-system-dns"></a>Sistema de Nomes de Domínio (DNS)
<a name="DNS"> </a>

Skype para Business Server 2015 requer o DNS, pelos seguintes motivos:
  
- DNS permite Skype para negócios 2015 de servidor descobrir servidores ou pools, internos permitindo para comunicações de servidor-para-servidor.
    
- DNS permite que clientes máquinas descubram o pool de Front-End ou servidor Standard Edition que está sendo usado para transações SIP.
    
- Ele associa URLs simples para conferências aos servidores que as hospedam.
    
- DNS permite que usuários externos e computadores cliente se conectem aos servidores de borda, ou o proxy reverso HTTP para mensagens instantâneas (IM) ou conferência.
    
- Ele permite que as comunicações unificadas (UC) dispositivos que não são registrados no descubram o pool de Front-End ou o servidor Standard Edition que está executando o serviço web de atualização de dispositivo para obter atualizações e enviem logs.
    
- O uso do DNS permite que clientes móveis descubram automaticamente os recursos dos serviços Web sem que os usuários tenham que inserir URLs manualmente em suas configurações do dispositivo.
    
- E também é usado no balanceamento de carga do DNS.
    
É importante observar que Skype para Business Server 2015 não dá suporte a nomes de domínio internacionalizados (IDNs).
  
E é extremamente importante lembrar que qualquer nome no DNS ser idêntica ao nome do computador configurado em qualquer servidor que está sendo usado pelo Skype para Business Server 2015. Especificamente, estamos não podem ter qualquer short-nomes no ambiente e devem ter os FQDNs do construtor de topologias.
  
Isso parece seria lógica para qualquer computador que já está associado a um domínio, mas se você tiver um servidor de borda que não está vinculada ao seu domínio, ele pode ter um valor padrão de um nome curto, com nenhum sufixo de domínio. Certifique-se de que não é o caso, no DNS ou no servidor de borda ou qualquer Skype para Business Server 2015 servidor ou pool, na verdade.
  
E definitivamente não use caracteres Unicode nem sublinhados. Os caracteres padrão (que fazem A-Z, a-z, 0-9 e hifens) são aqueles que vai ser suportados pelo DNS externo e as autoridades de certificação pública (você precisará atribuir FQDNs ao SN no certificado, não se esqueça), portanto, você vai substituição sozinho muito desgosto se nome com isso em mente.
  
Para saber mais sobre os requisitos do DNS para redes, consulte a seção [Networking](../../plan-your-deployment/network-requirements/network-requirements.md) da sua documentação de planejamento.
  
## <a name="certificates"></a>Certificados
<a name="Certs"> </a>

Uma das coisas mais importantes a fazer antes da implantação é verificar se os seus certificados estão corretos. Skype para Business Server 2015 precisa de uma infraestrutura de chave pública (PKI) para transport layer security (TLS) e conexões do mutual transport layer security (MTLS). Basicamente, para se comunicar com segurança de uma maneira padronizada, Skype para Business Server usa certificados emitidos por autoridades de certificação (CAs).
  
Estas são algumas coisas que Skype para Business Server 2015 usa certificados para:
  
- Conexões TLS entre clientes e servidores
    
- Conexões MTLS entre servidores
    
- Federação usando descoberta automática de parceiros no DNS
    
- Acesso de usuários remotos a IM (mensagens instantâneas)
    
- Acesso de usuário externo a sessões de A/V (áudio/vídeo), compartilhamento de aplicativos e conferência
    
- Comunicando com aplicativos da web e o Outlook Web Access (OWA)
    
Portanto o planejamento de certificado 's obrigatória. Agora, vejamos uma lista de algumas coisas que você precisa ter em mente ao solicitar certificados:
  
- Todos os certificados de servidor devem oferecer suporte à autorização de servidor (EKU de servidor).
    
- Todos os certificados de servidor devem conter um CDP (Ponto de Distribuição de CRL).
    
- Todos os certificados devem ser assinados usando um algoritmo de assinatura que seja compatível com o sistema operacional. Skype para Business Server 2015 suporta SHA-1 e SHA-2 suite de digest dimensiona (224, 256, 384 e 512 bits) e atende ou excede os requisitos de sistema operacional.
    
- Registro automático é suportado para servidores internos executando Skype para Business Server 2015.
    
- Registro automático não é suportado para Skype para os servidores de borda do Business Server 2015.
    
- Quando você envia uma solicitação de certificado baseado na web para uma autoridade de certificação do Windows Server 2003, você deve enviá-lo em um computador executando o Windows Server 2003 com SP2 ou Windows XP.
    
> [!NOTE]
> Embora o KB922706 dê suporte à resolução de problemas com o registro de certificados via Web em relação a um registro de Serviços de Certificados do Windows Server 2003 via Web, ele não permite o uso do Windows Server 2008, do Windows Vista nem do Windows 7 para solicitar um certificado de uma AC do Windows Server 2003. 
  
> [!NOTE]
> O uso do algoritmo de assinatura RSASSA-PSS não é permitido e pode levar a erros no login e a problemas de encaminhamento de chamadas, entre outros.  
  
- Os comprimentos de chave de criptografia de 1024, 2048 e 4096 são suportados. Comprimentos de pelo menos 2048 são recomendados.
    
- O algoritmo de hash de assinatura ou sumário padrão é RSA. Os algoritmos ECDH_P256, ECDH_P384 e ECDH_P521 também têm suporte.
    
Portanto, é muito serem levados em consideração e definitivamente, há uma variedade de níveis de confortável com solicitar certificados de uma autoridade de certificação. Daremos algumas diretrizes mais abaixo para tornar o seu planejamento mais simples possíveis.
  
### <a name="certificates-for-your-internal-servers"></a>Certificados para seus servidores internos

Você precisará de certificados para a maioria dos seus servidores internos e provavelmente, você obterá-los por uma autoridade de certificação interna (ou seja, um localizado em seu domínio). Se quiser, você pode solicitar esses certificados de uma AC externa (localizada na internet). Se você está se perguntando o que autoridade de certificação pública você deve ir, você pode visitar a lista de [parceiros de certificado de comunicação unificada](https://support.microsoft.com/kb/929395/en-us) .
  
Você também precisará certificados quando Skype para Business Server 2015 se comunica com outros aplicativos e servidores, como o Microsoft Exchange Server. Esse, obviamente, deve ser um certificado que possa ser usado por outros aplicativos e servidores de maneira suportada. Skype para Business Server 2015 e outros produtos da Microsoft suporte ao protocolo de autorização aberta (OAuth) para autorização e autenticação de servidor-para-servidor. Se estiver interessado neste, temos um artigo de planejamento adicional para OAuth e Skype para Business Server 2015.
  
Skype para Business Server 2015 também inclui o suporte para (sem exigir) certificados assinados usando a função de hash criptográfico SHA-256. Para oferecer suporte ao acesso externo usando SHA-256, o certificado externo é emitido por uma AC pública usando SHA-256.
  
Para tentar e manter as coisas simples, nós agrupamos os requisitos de certificado para servidores Standard Edition, pools Front-End e outras funções, em tabelas a seguir, com a empresa fictícia contoso.com sendo usados para exemplos (você provavelmente usará algo Else para seu ambiente). Todos esses são certificados do servidor Web padrão, com chaves privadas que não são exportáveis. Outras observações:
  
- O Uso Avançado de Chave (EKU) no servidor é automaticamente configurado quando o assistente de certificado é usado para solicitar certificados.
    
- Cada nome amigável do certificado deve ser exclusivo no repositório do computador.
    
- Conforme os exemplos de nomes abaixo, se você tiver configurado sipinternal.contoso.com ou sipexternal.contoso.com em seu DNS, eles precisam ser adicionado ao nome de alternativo de entidade (SAN) do certificado.
    
Certificados para servidores Standard Edition:
  
|**Certificado**|**Nome de entidade/nome comum**|**Nome alternativo de entidade**|**Exemplo**|**Comentários**|
|:-----|:-----|:-----|:-----|:-----|
|Padrão  <br/> |FQDN do pool  <br/> |FQDN do pool e FQDN do servidor  <br/> Se você tiver vários domínios SIP e tiver habilitado a configuração automática do cliente, o assistente de certificados detectará e adicionará os FQDNs de cada domínio SIP aceito.  <br/> Se esse pool for o servidor de logon automático para clientes, e a combinação estrita do Sistema de Nome de Domínio (DNS) for exigida na política do grupo, também serão necessárias entradas para o sip.sipdomain (para cada domínio de SIP que você tiver).  <br/> |SN=se01.contoso.com; SAN=se01.contoso.com  <br/> Se esse pool for o servidor de logon automático para clientes, e se a combinação estrita de DNS for exigida na política do grupo, também serão necessários: SAN=sip.contoso.com; SAN=sip.fabrikam.com  <br/> |No servidor do Standard Edition de servidores Standard Edition, o FQDN do servidor é igual ao FQDN do pool.  <br/> O assistente detecta quaisquer domínios SIP especificados durante a instalação e os adiciona automaticamente ao nome alternativo para a entidade.  <br/> Você também utiliza este certificado para Autenticação de Servidor para Servidor.  <br/> |
|Web interna  <br/> |FQDN do servidor  <br/> |Cada um dos seguintes:  <br/> • Internos da web FQDN (que é o mesmo que o FQDN do servidor)  <br/> AND  <br/> • Atender a URLs simples  <br/> • Dial-in de URL simples  <br/> • URL simples de Admin  <br/> OR  <br/> • Uma entrada curinga para URLs simples  <br/> |SN=se01.contoso.com; SAN=se01.contoso.com; SAN=meet.contoso.com; SAN=meet.fabrikam.com; SAN=dialin.contoso.com; SAN=admin.contoso.com  <br/> Como usar um certificado curinga:  <br/> SN=se01.contoso.com; SAN=se01.contoso.com; SAN =\*. contoso.com  <br/> |Você não pode substituir o FQDN no construtor de topologia de web interna.  <br/> Se você possui vários Atender a URLs simples, deve incluir todos eles como nomes alternativos de entidade.  <br/> As entradas curinga são suportadas pelas entradas de URL simples.  <br/> |
|Web externa  <br/> |FQDN do servidor  <br/> |Cada um dos seguintes:  <br/> • FQDN de web externa  <br/> AND  <br/> • Dial-in de URL simples  <br/> • Atender a URLs simples por domínio SIP  <br/> OR  <br/> • Uma entrada curinga para URLs simples  <br/> |SN=se01.contoso.com; SAN=webcon01.contoso.com; SAN=meet.contoso.com; SAN=meet.fabrikam.com; SAN=dialin.contoso.com  <br/> Como usar um certificado curinga:  <br/> SN=se01.contoso.com; SAN=webcon01.contoso.com; SAN =\*. contoso.com  <br/> |Se você tiver vários atender a URLs simples, você acaba de criar incluir todos eles como nomes de entidade alternativos.  <br/> As entradas curinga são suportadas pelas entradas de URL simples.  <br/> |
   
Certificados para servidores Front-End em um pool de Front-End:
  
|**Certificado**|**Nome de entidade/nome comum**|**Nome alternativo de entidade**|**Exemplo**|**Comentários**|
|:-----|:-----|:-----|:-----|:-----|
|Padrão  <br/> |FQDN do pool  <br/> |FQDN do pool e FQDN do servidor  <br/> Se você tiver vários domínios SIP e tiver habilitado a configuração automática do cliente, o assistente de certificados detectará e adicionará os FQDNs de cada domínio SIP aceito.  <br/> Se esse pool for o servidor de logon automático para clientes, e a combinação estrita do Sistema de Nome de Domínio (DNS) for exigida na política do grupo, também serão necessárias entradas para o sip.sipdomain (para cada domínio de SIP que você tiver).  <br/> |SN=eepool.contoso.com; SAN=eepool.contoso.com; SAN=ee01.contoso.com   <br/> Se esse pool for o servidor de logon automático para clientes, e se a combinação estrita de DNS for exigida na política do grupo, também serão necessários: SAN=sip.contoso.com; SAN=sip.fabrikam.com  <br/> |O assistente detecta quaisquer domínios SIP especificados durante a instalação e os adiciona automaticamente ao nome alternativo para a entidade.  <br/> Você também utiliza este certificado para Autenticação de Servidor para Servidor.  <br/> |
|Web interna  <br/> |FQDN do pool  <br/> |Cada um dos seguintes:  <br/> • Internos da web FQDN (que não é o mesmo que o FQDN do servidor)  <br/> • O FQDN do servidor  <br/> • Skype para o FQDN do pool de negócios  <br/> AND  <br/> • Atender a URLs simples  <br/> • Dial-in de URL simples  <br/> • URL simples de Admin  <br/> OR  <br/> • Uma entrada curinga para URLs simples  <br/> |SN=ee01.contoso.com; SAN=ee01.contoso.com; SAN=meet.contoso.com; SAN=meet.fabrikam.com; SAN=dialin.contoso.com; SAN=admin.contoso.com  <br/> Como usar um certificado curinga:  <br/> SN=ee01.contoso.com; SAN=ee01.contoso.com; SAN =\*. contoso.com  <br/> |Se você tiver vários atender a URLs simples, você acaba de criar incluir todos eles como nomes de entidade alternativos.  <br/> As entradas curinga são suportadas pelas entradas de URL simples.  <br/> |
|Web externa  <br/> |FQDN do pool  <br/> |Cada um dos seguintes:  <br/> • FQDN de web externa  <br/> AND  <br/> • Dial-in de URL simples  <br/> • URL simples de Admin  <br/> OR  <br/> • Uma entrada curinga para URLs simples  <br/> |SN=ee01.contoso.com; SAN=webcon01.contoso.com; SAN=meet.contoso.com; SAN=meet.fabrikam.com; SAN=dialin.contoso.com  <br/> Como usar um certificado curinga:  <br/> SN=ee01.contoso.com; SAN=webcon01.contoso.com; SAN =\*. contoso.com  <br/> |Se você tiver vários atender a URLs simples, você acaba de criar incluir todos eles como nomes de entidade alternativos.  <br/> As entradas curinga são suportadas pelas entradas de URL simples.  <br/> |
   
Certificados para o Diretor:
  
|**Certificado**|**Nome de entidade/nome comum**|**Nome alternativo de entidade**|**Exemplo**|
|:-----|:-----|:-----|:-----|
|Padrão  <br/> |Pool de diretores  <br/> |FQDN do diretor, FQDN do pool de diretores.  <br/> Se esse pool for o servidor de logon automático para clientes e estrita de DNS exigida na política de grupo, você também precisará entradas para sipdomain (para cada domínio SIP que você tiver).  <br/> |pool.contoso.com; SAN=dir01.contoso.com   <br/> Se esse pool de diretor for o servidor de logon automático para clientes e estrita de DNS for exigida na política de grupo, também serão precisos; SAN = SIP.Fabrikam.com  <br/> |
|Web interna  <br/> |FQDN do servidor  <br/> |Cada um dos seguintes:  <br/> • Internos da web FQDN (que é o mesmo que o FQDN do servidor)  <br/> • O FQDN do servidor  <br/> • Skype para o FQDN do pool de negócios  <br/> AND  <br/> • Atender a URLs simples  <br/> • Dial-in de URL simples  <br/> • URL simples de Admin  <br/> OR  <br/> • Uma entrada curinga para URLs simples  <br/> |SN=dir01.contoso.com; SAN=dir01.contoso.com; SAN=meet.contoso.com; SAN=meet.fabrikam.com; SAN=dialin.contoso.com; SAN=admin.contoso.com  <br/> Como usar um certificado curinga:  <br/> SN=dir01.contoso.com; SAN=dir01.contoso.com SAN =\*. contoso.com  <br/> |
|Web externa  <br/> |FQDN do servidor  <br/> |Cada um dos seguintes:  <br/> • FQDN de web externa  <br/> AND  <br/> • Atender a URLs simples por domínio SIP  <br/> • Dial-in de URL simples  <br/> OR  <br/> • Uma entrada curinga para URLs simples  <br/> |A FQDN de web externa de diretores deve ser diferente do pool de Front-End ou servidor Front-End.  <br/> SN=dir01.contoso.com; SAN=directorwebcon01.contoso.com SAN=meet.contoso.com; SAN=meet.fabrikam.com; SAN=dialin.contoso.com  <br/> Como usar um certificado curinga:  <br/> SN=dir01.contoso.com; SAN=directorwebcon01.contoso.com SAN =\*. contoso.com  <br/> |
   
Certificados para o servidor de mediação autônomo:
  
|**Certificado**|**Nome de entidade/nome comum**|**Nome alternativo de entidade**|**Exemplo**|
|:-----|:-----|:-----|:-----|
|Padrão  <br/> |FQDN do pool  <br/> |FQDN do pool  <br/> FQDN do servidor membro do pool  <br/> |SN=medsvr-pool.contoso.net; SAN=medsvr-pool.contoso.net; SAN=medsvr01.contoso.net  <br/> |
   
Certificados para aparelho de filial persistente:
  
|**Certificado**|**Nome de entidade/nome comum**|**Nome alternativo de entidade**|**Exemplo**|
|:-----|:-----|:-----|:-----|
|Padrão  <br/> |FQDN do aplicativo  <br/> |SIP. \<sipdomain\> (necessário apenas uma entrada por domínio SIP)  <br/> |SN=sba01.contoso.net; SAN=sip.contoso.com; SAN=sip.fabrikam.com  <br/> |
   
### <a name="certificates-for-your-persistent-chat-server"></a>Certificados para seu Servidor de Chat Persistente

Durante a instalação do seu servidor de Chat persistente, você vai precisar de um certificado emitido pela mesma CA que o usado pelo seu Skype para servidores internos do Business Server 2015. Isso precisa ser feito para cada servidor que executa o Persistent Chat serviços Web para Upload/Download de arquivo. É altamente recomendável que você tenha os certificados necessários antes de começar sua instalação do Chat persistente, e se a autoridade de certificação é externa, ainda mais (essas coisas podem demorar um pouco tempo para ser emitido).
  
### <a name="certificates-for-external-user-access-edge"></a>Certificados para acesso de usuário externo (Borda)

Skype para Business Server 2015 suporta o uso de um **único certificado público** para o acesso e web conferência interfaces externas de borda, além de A / o serviço de autenticação de V, que é fornecido por meio de todos os servidores de borda. Sua interface interna da borda normalmente usará um certificado privado emitido pela autoridade de certificação interna, mas se você preferir, você pode usar um certificado público para que isso também se ela for proveniente de uma autoridade de certificação confiável.
  
Seu proxy reverso (RP) também usará um certificado público que criptografa a comunicação entre o RP e os clientes e entre o RP e os servidores internos usando HTTP (ou, mais precisamente, TLS sobre HTTP).
  
### <a name="certificates-for-mobility"></a>Certificados para mobilidade

Se você estiver implantando mobilidade e você está apoiando descoberta automática para clientes móveis, você vai precisar incluir algumas entradas de nome alternativo da entidade adicionais em seus certificados para oferecer suporte as conexões seguras entre os clientes móveis.
  
Quais certificados? Você precisará de nomes SAN para descoberta automática nos certificados em:
  
- Pool de diretores
    
- Pool de Front-Ends
    
- Proxy reverso
    
As especificações serão listadas em cada tabela abaixo.
  
Agora, isso é onde um pouco de planejamento prévio é bom, mas às vezes você implantou Skype para Business Server 2015 sem pretende implantar a mobilidade e que vem para cima para baixo a linha quando você já tiver certificados em seu ambiente. Reemitir certificados através da AC interna costuma ser uma tarefa fácil, mas no caso de certificados públicos de uma AC pública, a reemissão pode custar caro.
  
Se esse for o que você estiver examinando e se você tiver muitos dos domínios SIP (o que tornaria adicionando SANS mais caro), você pode configurar o proxy reverso para utilizar HTTP para a solicitação inicial de Autodiscover Service, em vez de usar o HTTPS (que é o padrão configuração). O tópico Planejamento para Mobilidade traz mais informações sobre esse assunto.
  
Requisitos de certificado do pool de diretor e o pool de Front-End:
  
|**Descrição**|**Entrada do SAN**|
|:-----|:-----|
|URL interna do serviço de Descoberta Automática  <br/> |SAN = lyncdiscoverinternal. \<sipdomain\>  <br/> |
|URL externa do serviço de Descoberta Automática  <br/> |SAN = lyncdiscover. \<sipdomain\>  <br/> |
   
Como alternativa, é possível usar SAN =\*. \<sipdomain\>
  
Requisitos de certificado de proxy reverso (AC pública):
  
|**Descrição**|**Entrada do SAN**|
|:-----|:-----|
|URL externa do serviço de Descoberta Automática  <br/> |SAN = lyncdiscover. \<sipdomain\>  <br/> |
   
Este SAN precisa ser atribuído ao certificado que, por sua vez, é atribuído ao Ouvinte do SSL em seu proxy reverso.
  
> [!NOTE]
> Passando do seu ouvinte de proxy reverso que SANs para suas URLs de serviços Web externos. Alguns exemplos seria SAN=skypewebextpool01.contoso.com e dirwebexternal.contoso.com, se você implantou o diretor, (que é opcional). 
  
## <a name="file-share"></a>Compartilhamento de arquivo
<a name="Fileshare"> </a>

Skype para Business Server 2015 é capaz de usar o compartilhamento de arquivo a mesma para todo o armazenamento de arquivo. Deve-se ter em mente:
  
- Um compartilhamento de arquivo precisa estar em um armazenamento anexado direto (DAS) ou em uma rede de área de armazenamento (SAN), e isso inclui o sistema de arquivos distribuído (DFS), bem como uma matriz redundante de RAID para repositórios de arquivos. Para obter mais leitura em DFS para o Windows Server 2012, confira [esta página DFS](https://technet.microsoft.com/en-us/library/jj127250.aspx).
    
- Recomendamos um cluster compartilhado para o compartilhamento de arquivo. Se você estiver usando uma, você deve cluster Windows Server 2012 ou Windows Server 2012 R2. Windows Server 2008 R2 também é aceitável. Por que o Windows mais recente? Versões antigas podem não ter as permissões adequadas para habilitar todos os recursos. Você pode usar o administrador de Cluster para criar os compartilhamentos de arquivo e este artigo [como criar compartilhamentos de arquivos em um cluster de](https://support.microsoft.com/en-us/help/224967/how-to-create-file-shares-on-a-cluster) ajudá-lo com esses detalhes.
    
> [!CAUTION] 
> Você deve saber que o uso de NAS como compartilhamento de arquivo não é compatível; portanto, use uma das opções listadas acima. 
  

