---
title: Requisitos de ambiente para o Skype for Business Server 2015
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/15/2018
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 4812c444-2546-48d7-9ca7-b71fce508ed8
description: 'Resumo: Configure seus requisitos de não-servidor para o Skype for Business Server 2015. Há várias coisas que você deve configurar antes de realizar a implantação, incluindo Active Directory, DNS, certificados e compartilhamento de fileshares.'
ms.openlocfilehash: 60244391a04b1bab31464bd0ef0b804510e40955
ms.sourcegitcommit: 2cb46af39a0d116e8fd020aa04bd2ecbd6998a5f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/03/2020
ms.locfileid: "41678955"
---
# <a name="environmental-requirements-for-skype-for-business-server-2015"></a>Requisitos de ambiente para o Skype for Business Server 2015
 
**Resumo:** Configure seus requisitos de não-servidor para o Skype for Business Server 2015. Há várias coisas que você deve configurar antes de realizar a implantação, incluindo Active Directory, DNS, certificados e compartilhamento de fileshares.
  
Qual é o requisito ambiental para o Skype for Business Server 2015? Bem, colocamos tudo que não é um servidor diretamente relacionado a este tópico, para que você não precise fazer tantas coisas ao clicar. Se você estiver procurando por pré-requisitos de servidor, confira os [requisitos do servidor do Skype for Business Server 2015](server-requirements.md) doc. o[planejamento de rede](../../plan-your-deployment/network-requirements/network-requirements.md) também está documentado separadamente. Caso contrário, é o que temos neste artigo:
  
- [Active Directory](environmental-requirements.md#AD)
  
- [DNS (Sistema de Nomes de Domínio)](environmental-requirements.md#DNS)
  
- [Certificados](environmental-requirements.md#Certs)
  
- [Compartilhamento de arquivos](environmental-requirements.md#Fileshare)
  
## <a name="active-directory"></a>Active Directory
<a name="AD"> </a>

Embora muitos dados de configuração para servidores e serviços estejam armazenados no repositório de gerenciamento central do Skype for Business Server 2015, existem algumas coisas ainda armazenadas no Active Directory:
  
|**Objetos do Active Directory**|**Tipos de objeto**|
|:-----|:-----|
|Extensões de esquema  <br/> |Extensões de objetos de usuário  <br/> |
||Extensões do Lync Server 2013 e Lync Server 2010 para manter a compatibilidade com versões anteriores com suporte.  <br/> |
|Dados  <br/> |URI do SIP do usuário e outras configurações de usuário  <br/> |
||Objetos de contato para aplicativos (como o aplicativo grupo de resposta e o aplicativo de assistente de conferência).  <br/> |
||Dados publicados para compatibilidade com versões anteriores.  <br/> |
||Um SCP (ponto de controle de serviço) para o repositório de gerenciamento central.  <br/> |
||Conta de autenticação Kerberos (um objeto de computador opcional).  <br/> |
   
### <a name="os-for-domain-controllers"></a>OS para controladores de domínio

Portanto, qual OS para controladores de domínio pode ser usada? Temos a seguinte lista:

- Windows Server 2019 (você deve ter o Skype for Business Server 2015 atualização cumulativa 5 ou posterior)
  
- Windows Server 2016
    
- Windows Server 2012 R2
    
- Windows Server 2012
    
- Windows Server 2008 R2
    
- Windows Server 2008
    
Agora, o nível funcional do domínio de qualquer domínio no qual você implanta o Skype for Business Server 2015 e o nível funcional da floresta de todas as quais você implanta o Skype for Business Server 2015 em, precisam ser um dos seguintes:

- Windows Server 2019 (você deve ter o Skype for Business Server 2015 atualização cumulativa 5 ou posterior)
  
- Windows Server 2016
    
- Windows Server 2012 R2
    
- Windows Server 2012
    
- Windows Server 2008 R2
    
- Windows Server 2008
    
- Windows Server 2003
    
É possível ter controladores de domínio somente leitura nesses ambientes? Sim, desde que também haja controladores de domínio graváveis disponíveis.
  
Agora, é importante saber que o Skype for Business Server 2015 não é compatível com domínios de rótulo único. O que são esses domínios? Se você tiver um domínio raiz chamado contoso. local, isso vai funcionar bem. Se você tiver um domínio raiz chamado de local, isso não funcionará, e isso não será compatível como resultado. Um pouco mais sobre isso foi escrito neste [artigo da base de dados de conhecimento](https://support.microsoft.com/kb/300684/en-us).
  
O Skype for Business Server 2015 também não permite a renomeação de domínios. Se você realmente tem que fazer isso, será necessário desinstalar o Skype for Business Server 2015, fazer a renomeação de domínio e, em seguida, reinstalar o Skype for Business Server 2015.
  
Por fim, você pode estar lidando com um domínio com um ambiente de AD DS bloqueado e tudo certo. Temos mais informações sobre como implantar o Skype for Business Server 2015 nesse tipo de ambiente nos documentos de implantação.
  
### <a name="ad-topologies"></a>Topologias do AD

As topologias compatíveis com o Skype for Business Server 2015 são:
  
- Floresta única com domínio único
    
- Floresta única com uma única árvore e vários domínios
    
- Floresta única com várias árvores e namespaces não contíguos
    
- Várias florestas em uma topologia de floresta central
    
- Várias florestas em uma topologia de floresta de recursos
    
- Várias florestas em uma topologia de floresta de recursos do Skype for Business com o Exchange Online
    
- Várias florestas em uma topologia de floresta de recursos com Skype for Business Online e Azure Active Directory Connect
    
Temos diagramas e descrições para ajudá-lo a determinar qual topologia você tem em seu ambiente ou o que talvez seja necessário configurar antes de instalar o Skype for Business Server 2015. Para simplificar, também estamos incluindo uma chave:
  
![O é uma chave para os ícones usados nos diagramas de topologia do Skype for Business](../../media/cc0dbc17-cf81-4b79-bf99-4614cc6828a0.png)
  
#### <a name="single-forest-with-single-domain"></a>Floresta única com domínio único

![Diagrama de uma única floresta do Active Directory com um único domínio](../../media/24921a0b-3a3e-4bad-8427-49300e2e3f7a.png)
  
Não fica mais fácil do que isso, é uma floresta de domínio única, que é uma topologia comum.
  
#### <a name="single-forest-with-a-single-tree-and-multiple-domains"></a>Floresta única com uma única árvore e vários domínios

![Um único diagrama de floresta, árvore única e domínios do mutiple](../../media/63b9f0dd-6bac-4ba9-ae68-8be032d09dcb.png)
  
Esse diagrama mostra uma floresta única, mas ela também tem um ou mais domínios filho (há três deles neste exemplo específico). Portanto, o domínio no qual os usuários são criados pode ser diferente do domínio no qual o Skype for Business Server 2015 é implantado. Por que isso é relevante? É importante lembrar que quando você implanta um pool de front-end do Skype for Business Server, todos os servidores nesse pool precisam estar em um único domínio. Você pode ter administração entre domínios por meio do suporte do Skype for Business Server aos grupos de administradores universais do Windows.
  
De volta ao diagrama acima, você pode ver que os usuários de um domínio podem acessar pools do Skype for Business Server do mesmo domínio ou de domínios diferentes, mesmo se esses usuários estiverem em um domínio filho.
  
#### <a name="single-forest-with-multiple-trees-and-disjoint-namespaces"></a>Floresta única com várias árvores e namespaces não contíguos

![Um único floresta, várias árvores e diagramas de namespaces de desjunção](../../media/5ede77a1-f5d2-499c-a2c8-d02f3c2f7cd7.png)
  
Pode ser que você tenha uma topologia semelhante a este diagrama, onde você tem uma floresta, mas dentro dessa floresta há vários domínios, com namespaces de anúncios separados. Se esse for o caso, esta é uma boa ilustração do diagrama, pois temos usuários em três domínios diferentes acessando o Skype for Business Server 2015. Linhas sólidas indicam que elas estão acessando um pool do Skype for Business Server em seu próprio domínio, enquanto uma linha tracejada indica que elas estão indo para um pool em uma árvore diferente.
  
Como você pode ver, usuários no mesmo domínio, na mesma árvore ou mesmo em uma árvore diferente conseguem acessar os pools com sucesso.
  
#### <a name="multiple-forests-in-a-central-forest-topology"></a>Várias florestas em uma topologia de floresta central

![Várias florestas em um diagrama de topologia de floresta central](../../media/fec40746-4254-4c84-86b9-aad4a616ea2f.png)
  
O Skype for Business Server 2015 oferece suporte a várias florestas configuradas em uma topologia de floresta central. Se você não tiver certeza de que é o que você tem, a floresta central na topologia usa objetos nele para representar usuários nas outras florestas e hospeda contas de usuário para qualquer usuário da floresta.
  
Como isso funciona? Bem, um produto de sincronização de diretório (como o Forefront Identity Manager ou FIM) gerencia as contas de usuário da sua organização durante a existência. Quando uma conta é criada ou excluída de uma floresta, essa mudança é sincronizada até o contato correspondente na floresta central.
  
É claro que, se a sua infraestrutura de anúncios estiver no local, a movimentação para essa topologia pode não ser fácil, mas se você já estiver lá ou ainda estiver planejando a infraestrutura da floresta, essa pode ser uma boa opção. Você pode centralizar a implantação do Skype for Business Server 2015 em uma única floresta, enquanto os usuários podem pesquisar, comunicar e visualizar a presença de outros usuários em qualquer floresta. Todas as atualizações de contato são feitas automaticamente com o software de sincronização.
  
#### <a name="multiple-forests-in-a-skype-for-business-resource-forest-topology"></a>Várias florestas em uma topologia de floresta de recursos do Skype for Business
<a name="BKMK_multipleforestopology"> </a>

![Várias florestas em um diagrama de topologia de floresta de recursos](../../media/41efa3b6-d9e6-47df-992b-fefcfc39a80d.png)
  
Também há suporte para uma topologia de floresta de recursos; é onde uma floresta é dedicada à execução de aplicativos do servidor, como o Microsoft Exchange Server e o Skype for Business Server 2015. Essas florestas de recursos também hospedam uma representação sincronizada de objetos de usuário ativo, mas não contas de usuário habilitadas para logon. Portanto, a floresta de recursos é um ambiente de serviços compartilhados para outras florestas nas quais os objetos de usuários residem, e que têm uma relação de confiança no nível de floresta com a floresta de recursos.
  
Observe que o Exchange Server pode ser implantado na mesma floresta de recursos que o Skype for Business Server ou em uma floresta diferente.
  
Para implantar o Skype for Business Server 2015 nesse tipo de topologia, crie um objeto de usuário desabilitado na floresta de recursos para cada conta de usuário nas florestas do usuário (se o Microsoft Exchange Server já estiver no ambiente, isso pode ser feito para você). Em seguida, você precisará de uma ferramenta de sincronização de diretório (como Forefront Identity Manager ou FIM) para gerenciar contas de usuário durante o ciclo de vida.
  
#### <a name="multiple-forests-in-a-skype-for-business-resource-forest-topology-with-exchange-online"></a>Várias florestas em uma topologia de floresta de recursos do Skype for Business com o Exchange Online
<a name="BKMK_multipleforestopology"> </a>

Esta topologia é similar à topologia descrita em [Várias florestas em uma topologia de floresta de recursos do Skype for Business](environmental-requirements.md#BKMK_multipleforestopology).
  
Nessa topologia, há uma ou mais florestas do usuário, e o Skype for Business Server é implantado em uma floresta de recursos dedicada. O Exchange Server pode ser implantado no mesmo local na mesma floresta de recursos ou em uma floresta diferente e configurada para híbrido com o Exchange Online, ou os serviços de email podem ser fornecidos exclusivamente pelo Exchange Online para as contas locais. Não há um diagrama disponível para esta topologia.
  
#### <a name="multiple-forests-in-a-resource-forest-topology-with-skype-for-business-online-and-azure-active-directory-connect"></a>Várias florestas em uma topologia de floresta de recursos com Skype for Business Online e Azure Active Directory Connect
<a name="BKMK_multipleforestopology"> </a>

![Mostra duas florestas de anúncios, uma floresta de usuário e uma floresta de recursos. As duas florestas têm uma relação de confiança. Eles são sincronizados com o Office 365 usando o Azure AD Connect. Todos os usuários estão habilitados para o Skype for Business por meio do Office 365.](../../media/6d54558d-8786-4ebf-90f6-55ae3fdb5ae7.jpg)
  
Neste cenário há várias florestas locais, com uma topologia de floresta de recursos. Há um relacionamento de total confiança entre as florestas do Active Directory. A ferramenta Azure Active Directory Connect é usada para sincronizar contas entre as florestas de usuários locais e o Office 365.
  
 A organização também tem o Office 365 e usa o [Azure Active Directory Connect](https://go.microsoft.com/fwlink/p/?LinkId=614836) para sincronizar suas contas locais com o Office 365. Os usuários habilitados para o Skype for Business são habilitados via Office 365 e Skype for Business online. O Skype for Business Server não é implantado no local.
  
A autenticação de logon único é fornecida por um farm de serviços de Federação do Active Directory localizado na floresta do usuário.
  
Nesse cenário, é possível implantar o Exchange local, o Exchange Online, uma solução híbrida do Exchange ou não ter o Exchange implantado. O diagrama mostra somente o Exchange no Local, mas as outras soluções do Exchange são totalmente aceitas.
  
#### <a name="multiple-forests-in-a-resource-forest-topology-with-hybrid-skype-for-business"></a>Várias florestas em uma topologia de floresta de recursos com o Skype for Business híbrido 
<a name="BKMK_multipleforestopology"> </a>

Nesse cenário, há uma ou mais florestas de usuários locais, e o Skype for Business é implantado em uma floresta de recursos dedicada e está configurado para o modo híbrido com o Skype for Business online. O Exchange Server pode ser implantado no mesmo local na mesma floresta de recursos ou em uma floresta diferente e pode ser configurado para híbrido com o Exchange Online. Como alternativa, os serviços de email podem ser fornecidos exclusivamente pelo Exchange Online para as contas locais.
  
Para obter mais informações, consulte [configurar um ambiente de várias florestas para o Skype for Business híbrido](../../skype-for-business-hybrid-solutions/deploy-hybrid-connectivity/configure-a-multi-forest-environment-for-hybrid.md).
  
## <a name="domain-name-system-dns"></a>Sistema de Nomes de Domínio (DNS)
<a name="DNS"> </a>

O Skype for Business Server 2015 requer o DNS, pelos seguintes motivos:
  
- O DNS permite que o Skype for Business Server 2015 descubra servidores ou pools internos, permitindo comunicações entre servidores.
    
- O DNS permite que máquinas clientes descubram o pool de front-end ou o servidor Standard Edition sendo usado para transações SIP.
    
- Ele associa URLs simples para conferências aos servidores que as hospedam.
    
- O DNS permite que usuários externos e máquinas cliente se conectem a seus servidores de borda ou ao proxy de reverso HTTP para mensagens instantâneas (IM) ou conferência.
    
- Ele permite que dispositivos de comunicação unificada (UC) não estejam registrados descubram o pool de front-end ou o servidor Standard Edition que está executando o serviço Web de atualização de dispositivos para obter atualizações e enviar logs.
    
- O uso do DNS permite que clientes móveis descubram automaticamente os recursos dos serviços Web sem que os usuários tenham que inserir URLs manualmente em suas configurações do dispositivo.
    
- E também é usado no balanceamento de carga do DNS.
    
É importante observar que o Skype for Business Server 2015 não é compatível com os IDNs (nomes de domínio internacionalizados).
  
E é extremamente importante lembrar que qualquer nome no DNS é idêntico ao nome do computador configurado em qualquer servidor usado pelo Skype for Business Server 2015. Especificamente, não podemos ter nomes curtos no ambiente e devem ter FQDNs para o construtor de topologias.
  
Isso parece ser lógico para qualquer computador que já ingressou em um domínio, mas se você tiver um servidor de borda que não ingressou em seu domínio, ele poderá ter um nome curto, sem nenhum sufixo de domínio. Certifique-se de que não seja o caso, em DNS ou no servidor de borda, ou qualquer servidor ou pool do Skype for Business Server 2015, para isso.
  
E definitivamente não use caracteres Unicode ou sublinhados. Os caracteres padrão (que são a-Z, a-z, 0-9 e hifens) são aqueles que serão compatíveis com as autoridades de certificação DNS e públicas externas (você precisará atribuir FQDNs ao SN no certificado, não esqueça), portanto, você se reservará uma grande quantidade de Grief se Você se nomeu com isso em mente.
  
Para saber mais sobre os requisitos do DNS para redes, consulte a seção [Networking](../../plan-your-deployment/network-requirements/network-requirements.md) da sua documentação de planejamento.
  
## <a name="certificates"></a>Certificados
<a name="Certs"> </a>

Uma das coisas mais importantes a fazer antes da implantação é verificar se os seus certificados estão corretos. O Skype for Business Server 2015 precisa de uma PKI (infraestrutura de chave pública) para conexões de Transport Layer Security (TLS) e Mutual Transport Layer Security (MTLS). Basicamente, para comunicar-se com segurança de forma padronizada, o Skype for Business Server usa certificados emitidos por autoridades de certificação (CAs).
  
Estas são algumas das coisas que o Skype for Business Server 2015 usa certificados para:
  
- Conexões TLS entre clientes e servidores
    
- Conexões MTLS entre servidores
    
- Federação usando descoberta automática de parceiros no DNS
    
- Acesso de usuários remotos a IM (mensagens instantâneas)
    
- Acesso de usuário externo a sessões de A/V (áudio/vídeo), compartilhamento de aplicativos e conferência
    
- Conversando com aplicativos da Web e o Outlook Web Access (OWA)
    
Portanto, o planejamento de certificado deve. Agora, vamos examinar uma lista de algumas das coisas que você precisa ter em mente ao solicitar certificados:
  
- Todos os certificados de servidor devem oferecer suporte à autorização de servidor (EKU de servidor).
    
- Todos os certificados de servidor devem conter um CDP (Ponto de Distribuição de CRL).
    
- Todos os certificados devem ser assinados usando um algoritmo de assinatura que seja compatível com o sistema operacional. O Skype for Business Server 2015 é compatível com o conjunto de resumos SHA-1 e SHA-2 (224, 256, 384 e 512-bit) e atende ou supera os requisitos do sistema operacional.
    
- O registro automático tem suporte para servidores internos que executam o Skype for Business Server 2015.
    
- Não há suporte para a inscrição automática em servidores de borda do Skype for Business Server 2015.
    
- Ao enviar uma solicitação de certificado baseada na Web para uma autoridade de certificação do Windows Server 2003, você deve enviá-la a partir de um computador que esteja executando o Windows Server 2003 com SP2 ou Windows XP.
    
> [!NOTE]
> Embora o KB922706 dê suporte à resolução de problemas com o registro de certificados via Web em relação a um registro de Serviços de Certificados do Windows Server 2003 via Web, ele não permite o uso do Windows Server 2008, do Windows Vista nem do Windows 7 para solicitar um certificado de uma AC do Windows Server 2003. 
  
> [!NOTE]
> O uso do algoritmo de assinatura RSASSA-PSS não é permitido e pode levar a erros no login e a problemas de encaminhamento de chamadas, entre outros.  

> [!NOTE]
> O Skype for Business Server 2015 não oferece suporte a certificados CNG.
  
- Os comprimentos de chave de criptografia de 1024, 2048 e 4096 são suportados. Comprimentos de pelo menos 2048 são recomendados.
    
- O algoritmo de hash de assinatura ou sumário padrão é RSA. Os algoritmos ECDH_P256, ECDH_P384 e ECDH_P521 também têm suporte.
    
Portanto, é muito preciso pensar e, definitivamente, há uma variedade de níveis de conforto com a solicitação de certificados de uma CA. Vamos dar a você mais algumas diretrizes a seguir para fazer seu planejamento o mais simples possível.
  
### <a name="certificates-for-your-internal-servers"></a>Certificados para seus servidores internos

Você precisará de certificados para a maioria dos seus servidores internos e, provavelmente, receberá uma CA interna (que é uma localizada no seu domínio). Se quiser, você pode solicitar esses certificados de uma AC externa (localizada na internet). Se você estiver se perguntando qual é a autoridade de certificação pública, pode dar uma olhada na lista de [parceiros do certificado de comunicação unificada](/SkypeForBusiness/certification/services-ssl) .
  
Você também precisará de certificados quando o Skype for Business Server 2015 se comunicar com outros aplicativos e servidores, como o Microsoft Exchange Server. Esse, obviamente, deve ser um certificado que possa ser usado por outros aplicativos e servidores de maneira suportada. O Skype for Business Server 2015 e outros produtos da Microsoft dão suporte ao protocolo de autorização aberta (OAuth) para autenticação e autorização de servidor para servidor. Se você estiver interessado nisso, temos um artigo de planejamento adicional para o OAuth e o Skype for Business Server 2015.
  
O Skype for Business Server 2015 também inclui suporte para (sem exigir) certificados assinados usando a função hash de criptografia SHA-256. Para oferecer suporte ao acesso externo usando SHA-256, o certificado externo é emitido por uma AC pública usando SHA-256.
  
Para experimentar e manter as coisas diretas, colocamos os requisitos de certificado para servidores de edição padrão, conjuntos de front-end e outras funções, nas tabelas a seguir, com o contoso.com fictício sendo usado para exemplos (você provavelmente usará algo mais para o seu ambiente). Todos esses são certificados do servidor Web padrão, com chaves privadas que não são exportáveis. Outras observações:
  
- O Uso Avançado de Chave (EKU) no servidor é automaticamente configurado quando o assistente de certificado é usado para solicitar certificados.
    
- Cada nome amigável do certificado deve ser exclusivo no repositório do computador.
    
- De acordo com os exemplos de nomes abaixo, se você configurou o sipinternal.contoso.com ou o sipexternal.contoso.com em seu DNS, ele precisará ser adicionado ao nome alternativo da entidade (SAN) do certificado.
    
Certificados para servidores Standard Edition:
  
|**Certificado**|**Nome de entidade/nome comum**|**Nome alternativo de entidade**|**Exemplo**|**Comentários**|
|:-----|:-----|:-----|:-----|:-----|
|Padrão  <br/> |FQDN do pool  <br/> |FQDN do pool e FQDN do servidor  <br/> Se você tiver vários domínios SIP e tiver habilitado a configuração automática do cliente, o assistente de certificados detectará e adicionará os FQDNs de cada domínio SIP aceito.  <br/> Se esse pool for o servidor de logon automático para clientes, e a combinação estrita do Sistema de Nome de Domínio (DNS) for exigida na política do grupo, também serão necessárias entradas para o sip.sipdomain (para cada domínio de SIP que você tiver).  <br/> |SN=se01.contoso.com; SAN=se01.contoso.com  <br/> Se esse pool for o servidor de logon automático para clientes, e se a combinação estrita de DNS for exigida na política do grupo, também serão necessários: SAN=sip.contoso.com; SAN=sip.fabrikam.com  <br/> |Nos servidores Standard Edition Standard Edition Server, o FQDN do servidor é o mesmo que o FQDN do pool.  <br/> O assistente detecta quaisquer domínios SIP especificados durante a instalação e os adiciona automaticamente ao nome alternativo para a entidade.  <br/> Você também utiliza este certificado para Autenticação de Servidor para Servidor.  <br/> |
|Web interna  <br/> |FQDN do servidor  <br/> |Cada um dos seguintes:  <br/> • FQDN da Web interno (que é o mesmo que o FQDN do servidor)  <br/> AND  <br/> • Conheça URLs simples  <br/> • URL simples discada  <br/> • URL simples de administrador  <br/> OR  <br/> • Uma entrada curinga para as URLs simples  <br/> |SN=se01.contoso.com; SAN=se01.contoso.com; SAN=meet.contoso.com; SAN=meet.fabrikam.com; SAN=dialin.contoso.com; SAN=admin.contoso.com  <br/> Como usar um certificado curinga:  <br/> SN = SE01. contoso. com; SAN = SE01. contoso. com; SAN =\*. contoso.com  <br/> |Não é possível substituir o FQDN da Web interna no construtor de topologias.  <br/> Se você possui vários Atender a URLs simples, deve incluir todos eles como nomes alternativos de entidade.  <br/> As entradas curinga são suportadas pelas entradas de URL simples.  <br/> |
|Web externa  <br/> |FQDN do servidor  <br/> |Cada um dos seguintes:  <br/> • FQDN da Web externo  <br/> AND  <br/> • URL simples discada  <br/> • Atender URLs simples por domínio SIP  <br/> OR  <br/> • Uma entrada curinga para as URLs simples  <br/> |SN=se01.contoso.com; SAN=webcon01.contoso.com; SAN=meet.contoso.com; SAN=meet.fabrikam.com; SAN=dialin.contoso.com  <br/> Como usar um certificado curinga:  <br/> SN = SE01. contoso. com; SAN = webcon01. contoso. com; SAN =\*. contoso.com  <br/> |Se você tiver várias URLs que atendem a URLs simples, você tem que incluir todas elas como nomes alternativos de assunto.  <br/> As entradas curinga são suportadas pelas entradas de URL simples.  <br/> |
   
Certificados para servidores front-end em um pool de front-ends:
  
|**Certificado**|**Nome de entidade/nome comum**|**Nome alternativo de entidade**|**Exemplo**|**Comentários**|
|:-----|:-----|:-----|:-----|:-----|
|Padrão  <br/> |FQDN do pool  <br/> |FQDN do pool e FQDN do servidor  <br/> Se você tiver vários domínios SIP e tiver habilitado a configuração automática do cliente, o assistente de certificados detectará e adicionará os FQDNs de cada domínio SIP aceito.  <br/> Se esse pool for o servidor de logon automático para clientes, e a combinação estrita do Sistema de Nome de Domínio (DNS) for exigida na política do grupo, também serão necessárias entradas para o sip.sipdomain (para cada domínio de SIP que você tiver).  <br/> |SN=eepool.contoso.com; SAN=eepool.contoso.com; SAN=ee01.contoso.com   <br/> Se esse pool for o servidor de logon automático para clientes, e se a combinação estrita de DNS for exigida na política do grupo, também serão necessários: SAN=sip.contoso.com; SAN=sip.fabrikam.com  <br/> |O assistente detecta quaisquer domínios SIP especificados durante a instalação e os adiciona automaticamente ao nome alternativo para a entidade.  <br/> Você também utiliza este certificado para Autenticação de Servidor para Servidor.  <br/> |
|Web interna  <br/> |FQDN do pool  <br/> |Cada um dos seguintes:  <br/> • FQDN interno da Web (que não é o mesmo que o FQDN do servidor)  <br/> • FQDN do servidor  <br/> • FQDN do pool do Skype for Business  <br/> AND  <br/> • Conheça URLs simples  <br/> • URL simples discada  <br/> • URL simples de administrador  <br/> OR  <br/> • Uma entrada curinga para as URLs simples  <br/> |SN=ee01.contoso.com; SAN=ee01.contoso.com; SAN=meet.contoso.com; SAN=meet.fabrikam.com; SAN=dialin.contoso.com; SAN=admin.contoso.com  <br/> Como usar um certificado curinga:  <br/> SN = ee01. contoso. com; SAN = ee01. contoso. com; SAN =\*. contoso.com  <br/> |Se você tiver várias URLs que atendem a URLs simples, você tem que incluir todas elas como nomes alternativos de assunto.  <br/> As entradas curinga são suportadas pelas entradas de URL simples.  <br/> |
|Web externa  <br/> |FQDN do pool  <br/> |Cada um dos seguintes:  <br/> • FQDN da Web externo  <br/> AND  <br/> • URL simples discada  <br/> • URL simples de administrador  <br/> OR  <br/> • Uma entrada curinga para as URLs simples  <br/> |SN=ee01.contoso.com; SAN=webcon01.contoso.com; SAN=meet.contoso.com; SAN=meet.fabrikam.com; SAN=dialin.contoso.com  <br/> Como usar um certificado curinga:  <br/> SN = ee01. contoso. com; SAN = webcon01. contoso. com; SAN =\*. contoso.com  <br/> |Se você tiver várias URLs que atendem a URLs simples, você tem que incluir todas elas como nomes alternativos de assunto.  <br/> As entradas curinga são suportadas pelas entradas de URL simples.  <br/> |
   
Certificados para o diretor:
  
|**Certificado**|**Nome de entidade/nome comum**|**Nome alternativo de entidade**|**Exemplo**|
|:-----|:-----|:-----|:-----|
|Padrão  <br/> |Pool de diretores  <br/> |FQDN do diretor, FQDN do pool de directors.  <br/> Se esse pool for o servidor de logon automático para clientes e a correspondência de DNS estrito for necessária na política de grupo, você também precisará de entradas para SIP. sipdomain (para cada domínio SIP que você tiver).  <br/> |pool.contoso.com; SAN=dir01.contoso.com   <br/> Se esse pool de diretor for o servidor de logon automático para clientes e a correspondência de DNS estrito for necessária na política de grupo, você também precisará de SAN = SIP. contoso. com; SAN = SIP. fabrikam. com  <br/> |
|Web interna  <br/> |FQDN do servidor  <br/> |Cada um dos seguintes:  <br/> • FQDN da Web interno (que é o mesmo que o FQDN do servidor)  <br/> • FQDN do servidor  <br/> • FQDN do pool do Skype for Business  <br/> AND  <br/> • Conheça URLs simples  <br/> • URL simples discada  <br/> • URL simples de administrador  <br/> OR  <br/> • Uma entrada curinga para as URLs simples  <br/> |SN=dir01.contoso.com; SAN=dir01.contoso.com; SAN=meet.contoso.com; SAN=meet.fabrikam.com; SAN=dialin.contoso.com; SAN=admin.contoso.com  <br/> Como usar um certificado curinga:  <br/> SN = dir01. contoso. com; SAN = dir01. contoso. com SAN =\*. contoso.com  <br/> |
|Web externa  <br/> |FQDN do servidor  <br/> |Cada um dos seguintes:  <br/> • FQDN da Web externo  <br/> AND  <br/> • Atender URLs simples por domínio SIP  <br/> • URL simples discada  <br/> OR  <br/> • Uma entrada curinga para as URLs simples  <br/> |O FQDN da Web externa do diretor deve ser diferente do pool de front-end ou do servidor front-end.  <br/> SN=dir01.contoso.com; SAN=directorwebcon01.contoso.com SAN=meet.contoso.com; SAN=meet.fabrikam.com; SAN=dialin.contoso.com  <br/> Como usar um certificado curinga:  <br/> SN = dir01. contoso. com; SAN = directorwebcon01. contoso. com SAN =\*. contoso.com  <br/> |
   
Certificados para servidor de mediação autônomo:
  
|**Certificado**|**Nome de entidade/nome comum**|**Nome alternativo de entidade**|**Exemplo**|
|:-----|:-----|:-----|:-----|
|Padrão  <br/> |FQDN do pool  <br/> |FQDN do pool  <br/> FQDN do servidor membro do pool  <br/> |SN=medsvr-pool.contoso.net; SAN=medsvr-pool.contoso.net; SAN=medsvr01.contoso.net  <br/> |
   
Certificados para aparelho de ramificação sobreviventes:
  
|**Certificado**|**Nome de entidade/nome comum**|**Nome alternativo de entidade**|**Exemplo**|
|:-----|:-----|:-----|:-----|
|Padrão  <br/> |FQDN do aplicativo  <br/> |SPI. \<sipdomain\> (você precisa apenas de uma entrada por domínio SIP)  <br/> |SN=sba01.contoso.net; SAN=sip.contoso.com; SAN=sip.fabrikam.com  <br/> |
   
### <a name="certificates-for-your-persistent-chat-server"></a>Certificados para seu Servidor de Chat Persistente

Ao instalar seu servidor de chat persistente, você precisará de um certificado emitido pela mesma CA que o usado pelos seus servidores internos do Skype for Business Server 2015. Isso precisa ser feito para cada servidor que está executando os serviços Web de chat persistente para o carregamento/download de arquivos. É altamente recomendável que você tenha o (s) certificado (s) necessário (s) antes de iniciar a instalação de chat persistente, e se a sua CA for externa, ainda mais (esses itens podem levar um tempo para ser emitido).
  
### <a name="certificates-for-external-user-access-edge"></a>Certificados para acesso de usuário externo (Borda)

O Skype for Business Server 2015 oferece suporte ao uso de um **único certificado público** para interfaces externas de Edge de acesso e Web ProPlus, além do serviço de autenticação a/V, que é fornecido por meio do (s) servidor (es) de borda. A interface interna do Edge geralmente usará um certificado particular emitido pela sua CA interna, mas se preferir, você também pode usar um certificado público para isso, se for de uma CA confiável.
  
Seu proxy reverso (RP) também usará um certificado público que criptografa a comunicação entre o RP e os clientes e entre o RP e os servidores internos usando HTTP (ou, mais precisamente, TLS sobre HTTP).
  
### <a name="certificates-for-mobility"></a>Certificados para mobilidade

Se você estiver implantando a mobilidade e estiver oferecendo suporte à descoberta automática para clientes móveis, será necessário incluir algumas entradas de nomes alternativos de entidades adicionais em seus certificados para dar suporte às conexões seguras dos clientes móveis.
  
Quais certificados? Você precisará de nomes SAN para descoberta automática nos certificados em:
  
- Pool de diretores
    
- Pool de Front-Ends
    
- Proxy reverso
    
As especificações serão listadas em cada tabela abaixo.
  
Agora, é aí que um pouco de planejamento é bom, mas às vezes você implantou o Skype for Business Server 2015 sem se pretender implantar a mobilidade, e isso é feito na linha quando você já tem certificados em seu ambiente. Reemitir certificados através da AC interna costuma ser uma tarefa fácil, mas no caso de certificados públicos de uma AC pública, a reemissão pode custar caro.
  
Se for o que você está vendo e se você tiver muitos domínios SIP (o que torna a adição de SANS mais dispendiosas), você pode configurar seu proxy reverso para usar HTTP para a solicitação de serviço de descoberta automática inicial, em vez de usar HTTPS (que é o padrão configuração). O tópico Planejamento para Mobilidade traz mais informações sobre esse assunto.
  
Requisitos do pool de directors e do certificado de pool de front-end:
  
|**Descrição**|**Entrada do SAN**|
|:-----|:-----|
|URL interna do serviço de Descoberta Automática  <br/> |SAN = lyncdiscoverinternal. \<sipdomain\>  <br/> |
|URL externa do serviço de Descoberta Automática  <br/> |SAN = lyncdiscover. \<sipdomain\>  <br/> |
   
Você também pode usar o SAN =\*. \<sipdomain\>
  
Requisitos de certificado de proxy reverso (AC pública):
  
|**Descrição**|**Entrada do SAN**|
|:-----|:-----|
|URL externa do serviço de Descoberta Automática  <br/> |SAN = lyncdiscover. \<sipdomain\>  <br/> |
   
Este SAN precisa ser atribuído ao certificado que, por sua vez, é atribuído ao Ouvinte do SSL em seu proxy reverso.
  
> [!NOTE]
> Seu ouvinte de proxy reverso vai ter SANs para as URLs de seus serviços Web externos. Alguns exemplos seriam SAN = skypewebextpool01. contoso. com e dirwebexternal.contoso.com, se você tiver implantado o diretor, (que é opcional). 
  
## <a name="file-share"></a>Compartilhamento de arquivo
<a name="Fileshare"> </a>

O Skype for Business Server 2015 é capaz de usar o mesmo compartilhamento de arquivo para todo o armazenamento de arquivos. Deve-se ter em mente:
  
- Um compartilhamento de arquivo precisa estar em um armazenamento anexado direto (DAS) ou em uma rede de área de armazenamento (SAN), e isso inclui o sistema de arquivos distribuído (DFS), bem como uma matriz redundante de RAID para repositórios de arquivos. Para ler mais sobre o DFS para Windows Server 2012, confira [esta página DFS](https://technet.microsoft.com/library/jj127250.aspx).
    
- Recomendamos um cluster compartilhado para o compartilhamento de arquivo. Se você estiver usando um deles, deve clusterizar o Windows Server 2012 ou o Windows Server 2012 R2. O Windows Server 2008 R2 também é aceitável. Por que as janelas mais recentes? Versões antigas podem não ter as permissões adequadas para habilitar todos os recursos. Você pode usar o administrador de clusters para criar os compartilhamentos de arquivos, e este procedimento [como criar compartilhamentos de arquivos em um](https://support.microsoft.com/en-us/help/224967/how-to-create-file-shares-on-a-cluster) artigo de cluster ajudará você com esses detalhes.
    
> [!CAUTION] 
> Você deve saber que o uso de NAS como compartilhamento de arquivo não é compatível; portanto, use uma das opções listadas acima. 
  

