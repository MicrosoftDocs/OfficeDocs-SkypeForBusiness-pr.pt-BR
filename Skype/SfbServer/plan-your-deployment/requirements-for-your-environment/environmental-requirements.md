---
title: Requisitos ambientais para o Skype for Business Server 2015
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
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
description: 'Resumo: Configure seus requisitos de não-servidor para o Skype for Business Server 2015. Há várias coisas que você deve configurar antes de realizar sua implantação, incluindo Active Directory, DNS, certs e fileshares.'
ms.openlocfilehash: d552c0c2c6b9f129b6dcf08e927634c6e3bdde6e
ms.sourcegitcommit: d69bad69ba9a9bca4614d72d8f34fb2a0a9e4dc4
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/13/2020
ms.locfileid: "44220871"
---
# <a name="environmental-requirements-for-skype-for-business-server-2015"></a>Requisitos ambientais para o Skype for Business Server 2015
 
**Resumo:** Configure seus requisitos de não-servidor para o Skype for Business Server 2015. Há várias coisas que você deve configurar antes de realizar sua implantação, incluindo Active Directory, DNS, certs e fileshares.
  
Qual é um requisito de ambiente para o Skype for Business Server 2015? Bem, colocamos tudo o que não está diretamente relacionado ao servidor neste tópico, para que você não precise fazer tantas tarefas. Se você estiver procurando por pré-requisitos de servidor, confira os requisitos de [servidor do Skype for Business Server 2015](server-requirements.md) doc. o[planejamento de rede](../../plan-your-deployment/network-requirements/network-requirements.md) também está documentado separadamente. Caso contrário, isso é o que temos neste artigo:
  
- [Active Directory](environmental-requirements.md#AD)
  
- [Domain Name System (DNS)](environmental-requirements.md#DNS)
  
- [Certificados](environmental-requirements.md#Certs)
  
- [Compartilhamento de arquivos](environmental-requirements.md#Fileshare)
  
## <a name="active-directory"></a>Active Directory
<a name="AD"> </a>

Embora vários dados de configuração para servidores e serviços estejam armazenados no repositório de gerenciamento central do Skype for Business Server 2015, há algumas coisas ainda armazenadas no Active Directory:
  
|**Objetos do Active Directory**|**Tipos de objeto**|
|:-----|:-----|
|Extensões de esquema  <br/> |Extensões do objeto do usuário  <br/> |
||Extensões para Lync Server 2013 e Lync Server 2010, para manter a compatibilidade com versões anteriores com suporte.  <br/> |
|Dados  <br/> |URI do SIP do usuário e outras configurações do usuário  <br/> |
||Objetos de contato para aplicativos (como o aplicativo de grupo de resposta e o aplicativo de atendedor de conferência).  <br/> |
||Dados publicados para compatibilidade com versões anteriores.  <br/> |
||Um ponto de controle de serviço (SCP) para o repositório de gerenciamento central.  <br/> |
||Conta de autenticação Kerberos (um objeto de computador opcional).  <br/> |
   
### <a name="os-for-domain-controllers"></a>Sistema operacional para controladores de domínio

Portanto, qual sistema operacional de controlador de domínio pode ser usado? Temos a seguinte lista:

- Windows Server 2019 (você deve ter o Skype for Business Server 2015 atualização cumulativa 5 ou posterior)
  
- Windows Server 2016
    
- Windows Server 2012 R2
    
- Windows Server 2012
    
- Windows Server 2008 R2
    
- Windows Server 2008
    
Agora, o nível funcional do domínio de qualquer domínio para o qual você implanta o Skype for Business Server 2015 e o nível funcional da floresta de qualquer floresta em que você implanta o Skype for Business Server 2015, precisa ser um dos seguintes:

- Windows Server 2019 (você deve ter o Skype for Business Server 2015 atualização cumulativa 5 ou posterior)
  
- Windows Server 2016
    
- Windows Server 2012 R2
    
- Windows Server 2012
    
- Windows Server 2008 R2
    
- Windows Server 2008
    
- Windows Server 2003
    
Você pode ter controladores de domínio somente leitura nesses ambientes? Certamente, contanto que haja controladores de domínio graváveis disponíveis no mesmo site que o Skype for Business Server.
  
Agora, é importante saber que o Skype for Business Server 2015 não oferece suporte a domínios com rótulo único. O que são? Se você tiver um domínio raiz chamado contoso. local, isso vai ser bom. Se você tiver um domínio raiz apenas chamado local, isso não funcionará e, como resultado, não será suportado. Um pouco mais sobre isso foi escrito neste [artigo da base de conhecimento](https://support.microsoft.com/kb/300684/en-us).
  
O Skype for Business Server 2015 também não dá suporte à renomeação de domínios. Se você realmente tiver feito isso, será necessário desinstalar o Skype for Business Server 2015, fazer o domínio renomear e, em seguida, reinstalar o Skype for Business Server 2015.
  
Por fim, você pode estar lidando com um domínio com um ambiente de AD DS bloqueado, e isso é tudo certo. Temos mais informações sobre como implantar o Skype for Business Server 2015 nesse tipo de ambiente nos documentos de implantação.
  
### <a name="ad-topologies"></a>Topologias do AD

As topologias suportadas do Skype for Business Server 2015 são:
  
- Floresta única com domínio único
    
- Floresta única com uma única árvore e vários domínios
    
- Floresta única com várias árvores e namespaces não contíguos
    
- Várias florestas em uma topologia de floresta central
    
- Várias florestas em uma topologia de floresta de recursos
    
- Várias florestas em uma topologia de floresta de recursos do Skype for Business com o Exchange Online
    
- Várias florestas em uma topologia de floresta de recursos com o Skype for Business Online e o Azure Active Directory Connect
    
Temos diagramas e descrições para ajudá-lo a determinar qual topologia você tem no seu ambiente ou o que você pode precisar configurar antes de instalar o Skype for Business Server 2015. Para simplificar, também estamos incluindo uma chave:
  
![O é uma chave para os ícones usados para diagramas de topologia do Skype for Business](../../media/cc0dbc17-cf81-4b79-bf99-4614cc6828a0.png)
  
#### <a name="single-forest-with-single-domain"></a>Floresta única com domínio único

![Diagrama da floresta única do Active Directory com um único domínio](../../media/24921a0b-3a3e-4bad-8427-49300e2e3f7a.png)
  
Não fica mais fácil do que isso, é uma floresta de domínio único, é uma topologia comum.
  
#### <a name="single-forest-with-a-single-tree-and-multiple-domains"></a>Floresta única com uma única árvore e vários domínios

![Um único diagrama de floresta, de árvore única e de domínios do vários](../../media/63b9f0dd-6bac-4ba9-ae68-8be032d09dcb.png)
  
Este diagrama mostra uma única floresta, novamente, mas também tem um ou mais domínios filho (há três neste exemplo específico). Portanto, o domínio no qual os usuários são criados pode ser diferente do domínio do Skype for Business Server 2015 que é implantado. Por que se preocupar com isso? É importante lembrar que quando você implanta um pool de front-ends do Skype for Business Server, todos os servidores desse pool precisam estar em um único domínio. Você pode ter a administração entre domínios por meio do suporte do Skype for Business Server dos grupos de administradores universais do Windows.
  
De volta ao diagrama acima, você pode ver que os usuários de um domínio podem acessar pools do Skype for Business Server do mesmo domínio ou de domínios diferentes, mesmo se esses usuários estiverem em um domínio filho.
  
#### <a name="single-forest-with-multiple-trees-and-disjoint-namespaces"></a>Floresta única com várias árvores e namespaces não contíguos

![Um diagrama de floresta única, várias árvores e namespaces não contíguos](../../media/5ede77a1-f5d2-499c-a2c8-d02f3c2f7cd7.png)
  
Pode ser que você tenha uma topologia semelhante a este diagrama, onde você tem uma floresta, mas dentro dessa floresta há vários domínios, com namespaces do AD separados. Se esse for o caso, esta é uma boa ilustração do diagrama, pois temos usuários em três domínios diferentes que acessam o Skype for Business Server 2015. As linhas sólidas indicam que eles estão acessando um pool do Skype for Business Server em seu próprio domínio, enquanto uma linha tracejada indica que eles estão acessando um pool em uma árvore diferente completamente.
  
Como você pode ver, os usuários no mesmo domínio, a mesma árvore ou até mesmo uma árvore diferente podem acessar pools com êxito.
  
#### <a name="multiple-forests-in-a-central-forest-topology"></a>Várias florestas em uma topologia de floresta central

![Várias florestas em um diagrama de topologia de floresta central](../../media/fec40746-4254-4c84-86b9-aad4a616ea2f.png)
  
O Skype for Business Server 2015 oferece suporte a várias florestas configuradas em uma topologia de floresta central. Se você não tiver certeza de que tem o que você tem, a floresta central na topologia usa objetos nela para representar usuários nas outras florestas e hospeda contas de usuário para qualquer usuário na floresta.
  
Como isso funciona? Bem, um produto de sincronização de diretório (como o Forefront Identity Manager ou FIM) gerencia as contas de usuário da sua organização por toda a sua existência. Quando uma conta é criada ou excluída de uma floresta, essa alteração é sincronizada para o contato correspondente na floresta central.
  
Obviamente, se sua infraestrutura do AD estiver migrando para essa topologia, talvez não seja fácil, mas se você já estiver lá ou ainda estiver planejando a infraestrutura da floresta, isso pode ser uma boa opção. Você pode centralizar a implantação do Skype for Business Server 2015 em uma única floresta, enquanto os usuários podem pesquisar, se comunicar e visualizar a presença de outros usuários em qualquer floresta. Todas as atualizações de contato de usuário são manipuladas automaticamente com o software de sincronização.
  
#### <a name="multiple-forests-in-a-skype-for-business-resource-forest-topology"></a>Várias florestas em uma topologia de floresta de recursos do Skype for Business
<a name="BKMK_multipleforestopology"> </a>

![Várias florestas em um diagrama de topologia de floresta de recursos](../../media/41efa3b6-d9e6-47df-992b-fefcfc39a80d.png)
  
Uma topologia de floresta de recursos também é suportada; é onde uma floresta é dedicada à execução de seus aplicativos de servidor, como o Microsoft Exchange Server e o Skype for Business Server 2015. Essas florestas de recursos também hospedam uma representação sincronizada de objetos de usuário ativos, mas nenhuma conta de usuário habilitada para logon. Portanto, a floresta de recursos é um ambiente de serviços compartilhados para outras florestas em que os objetos de usuário residem e têm uma relação de confiança de nível de floresta com a floresta de recursos.
  
Observe que o Exchange Server pode ser implantado na mesma floresta de recursos que o Skype for Business Server ou em uma floresta diferente.
  
Para implantar o Skype for Business Server 2015 nesse tipo de topologia, crie um objeto de usuário desabilitado na floresta de recursos para cada conta de usuário nas florestas do usuário (se o Microsoft Exchange Server já estiver no ambiente, isso pode ser feito para você). Em seguida, você precisará de uma ferramenta de sincronização de diretório (como o Forefront Identity Manager ou FIM) para gerenciar contas de usuário por meio do ciclo de vida.
  
#### <a name="multiple-forests-in-a-skype-for-business-resource-forest-topology-with-exchange-online"></a>Várias florestas em uma topologia de floresta de recursos do Skype for Business com o Exchange Online
<a name="BKMK_multipleforestopology"> </a>

Essa topologia é semelhante à topologia descrita em [várias florestas em uma topologia de floresta de recursos do Skype for Business](environmental-requirements.md#BKMK_multipleforestopology).
  
Nesta topologia, há uma ou mais florestas de usuários, e o Skype for Business Server é implantado em uma floresta de recursos dedicada. O Exchange Server pode ser implantado no local na mesma floresta de recursos ou em uma floresta diferente e configurado para híbrido com o Exchange Online, ou os serviços de email podem ser fornecidos exclusivamente pelo Exchange Online para as contas locais. Não há um diagrama disponível para essa topologia.
  
#### <a name="multiple-forests-in-a-resource-forest-topology-with-skype-for-business-online-and-azure-active-directory-connect"></a>Várias florestas em uma topologia de floresta de recursos com o Skype for Business Online e o Azure Active Directory Connect
<a name="BKMK_multipleforestopology"> </a>

![Mostra duas florestas do AD, uma floresta de usuário e uma floresta de recursos. As duas florestas têm uma relação de confiança. Eles estão sincronizados com o Microsoft 365 ou o Office 365 usando o Azure AD Connect. Todos os usuários estão habilitados para o Skype for Business via Microsoft 365 ou Office 365.](../../media/6d54558d-8786-4ebf-90f6-55ae3fdb5ae7.jpg)
  
Com esse cenário, há várias florestas no local, com uma topologia de floresta de recursos. Há uma relação de confiança total entre as florestas do Active Directory. A ferramenta Azure Active Directory Connect é usada para sincronizar contas entre as florestas do usuário local e o Microsoft 365 ou o Office 365.
  
 A organização também tem o Microsoft 365 ou o Office 365 e usa o [Azure Active Directory Connect](https://go.microsoft.com/fwlink/p/?LinkId=614836) para sincronizar suas contas locais com o Microsoft 365 ou o Office 365. Os usuários habilitados para o Skype for Business são habilitados via Microsoft 365 ou Office 365 e Skype for Business online. O Skype for Business Server não é implantado no local.
  
A autenticação de logon único é fornecida por um farm de serviços de Federação do Active Directory localizado na floresta do usuário.
  
Neste cenário, há suporte para implantar o Exchange local, o Exchange Online, uma solução híbrida do Exchange ou não ter o Exchange implantado. (O diagrama mostra somente o Exchange no local, mas as outras soluções do Exchange também são totalmente compatíveis).
  
#### <a name="multiple-forests-in-a-resource-forest-topology-with-hybrid-skype-for-business"></a>Várias florestas em uma topologia de floresta de recursos com Skype for Business híbrido
<a name="BKMK_multipleforestopology"> </a>

Neste cenário, há uma ou mais florestas de usuários locais, e o Skype for Business é implantado em uma floresta de recursos dedicada e é configurado para o modo híbrido com o Skype for Business online. O Exchange Server pode ser implantado no local na mesma floresta de recursos ou em uma floresta diferente e pode ser configurado para híbrido com o Exchange Online. Como alternativa, os serviços de email podem ser fornecidos exclusivamente pelo Exchange Online para as contas locais.
  
Para obter mais informações, consulte [configurar um ambiente de várias florestas para o Skype for Business híbrido](../../skype-for-business-hybrid-solutions/deploy-hybrid-connectivity/configure-a-multi-forest-environment-for-hybrid.md).
  
## <a name="domain-name-system-dns"></a>Domain Name System (DNS)
<a name="DNS"> </a>

O Skype for Business Server 2015 requer o DNS, pelos seguintes motivos:
  
- O DNS permite que o Skype for Business Server 2015 descubra servidores ou pools internos, permitindo a comunicação entre servidores.
    
- O DNS permite que máquinas clientes descubram o pool de front-ends ou o servidor Standard Edition que está sendo usado para transações SIP.
    
- Ele associa URLs simples a conferências com os servidores que hospedam essas conferências.
    
- O DNS permite que usuários externos e máquinas clientes se conectem aos servidores de borda ou ao proxy reverso HTTP, para mensagens instantâneas (IM) ou conferência.
    
- Ele permite que os dispositivos UC (comunicações unificadas) que não estão conectados descubram o pool de front-ends ou o servidor Standard Edition executando o serviço Web de atualização de dispositivo para obter atualizações e enviar logs.
    
- O uso de DNS permite que clientes móveis descubram automaticamente os recursos dos serviços Web sem exigir que os usuários insiram URLs manualmente nas configurações do dispositivo.
    
- E ele é usado no balanceamento de carga DNS.
    
É importante observar que o Skype for Business Server 2015 não dá suporte a IDNs (nomes de domínio internacionalizados).
  
E é extremamente importante lembrar que qualquer nome no DNS é idêntico ao nome do computador configurado em qualquer servidor que estiver sendo usado pelo Skype for Business Server 2015. Especificamente, não podemos ter nenhum nome curto no ambiente e deve ter FQDNs para o construtor de topologias.
  
Isso parece ser lógico para qualquer computador que já tenha ingressado em um domínio, mas se você tiver um servidor de borda que não ingressou no seu domínio, ele poderá ter um nome curto, sem nenhum sufixo de domínio. Certifique-se de que não é o caso, no DNS ou no servidor de borda, ou qualquer servidor ou pool do Skype for Business Server 2015, para esse assunto.
  
E definitivamente não use caracteres Unicode ou sublinhados. Os caracteres padrão (que são a-Z, a-z, 0-9 e hifens) são aqueles que serão suportados pelas autoridades de certificação públicas e de DNS externo (você precisará atribuir FQDNs ao SN no certificado, não esquecer), de modo que você se retorne uma grande quantidade de Grief se você se deparar com isso em mente.
  
Para ler mais sobre os requisitos de DNS para redes, confira a seção [rede](../../plan-your-deployment/network-requirements/network-requirements.md) da nossa documentação de planejamento.
  
## <a name="certificates"></a>Certificados
<a name="Certs"> </a>

Uma das coisas mais importantes que você pode fazer antes da implantação é garantir que você tenha seus certificados na ordem. O Skype for Business Server 2015 precisa de uma infraestrutura de chave pública (PKI) para conexões TLS e de protocolo de segurança de camada de transporte (MTLS). Basicamente, para se comunicar com segurança de forma padronizada, o Skype for Business Server usa certificados emitidos por autoridades de certificação (CAs).
  
Estas são algumas das coisas que o Skype for Business Server 2015 usa certificados para:
  
- Conexões TLS entre clientes e servidores
    
- Conexões MTLS entre servidores
    
- Usando de Federação para descoberta automática de DNS dos parceiros
    
- Acesso de usuários remotos a IM (mensagens instantâneas)
    
- Acesso de usuário externo a sessões de áudio/vídeo (AV), compartilhamento de aplicativos e conferência
    
- Conversando com aplicativos da Web e o Outlook Web Access (OWA)
    
Portanto, o planejamento de certificados é necessário. Agora, vamos dar uma olhada em uma lista de algumas das coisas que você precisa ter em mente ao solicitar certificados:
  
- Todos os certificados de servidor devem oferecer suporte à autorização de servidor (EKU de servidor).
    
- Todos os certificados de servidor devem conter um CDP (Ponto de Distribuição de CRL).
    
- Todos os certificados devem ser assinados usando um algoritmo de assinatura suportado pelo sistema operacional. O Skype for Business Server 2015 oferece suporte ao pacote de resumos SHA-1 e SHA-2 de tamanhos de resumo (224, 256, 384 e 512 bits) e atende ou supera os requisitos do sistema operacional.
    
- O registro automático é suportado para servidores internos que executam o Skype for Business Server 2015.
    
- O registro automático não é suportado para servidores de borda do Skype for Business Server 2015.
    
- Quando você envia uma solicitação de certificado baseado em web para uma AC Windows Server 2003, você deve submete-la de um computador que esteja executando Windows Server 2003 com SP2 ou Windows XP.
    
> [!NOTE]
> Embora o KB922706 forneça suporte para resolver problemas com a inscrição de certificados da Web em um registro na Web de serviços de certificados do Windows Server 2003, não é possível usar o Windows Server 2008, o Windows Vista ou o Windows 7 para solicitar um certificado de uma autoridade de certificação do Windows Server 2003. 
  
> [!NOTE]
> O uso do algoritmo de assinatura RSASSA-PSS não é suportado e pode levar a erros em problemas de encaminhamento de chamadas e login, entre outros problemas. 

> [!NOTE]
> O Skype for Business Server 2015 não suporta certificados CNG.
  
- Há suporte para os comprimentos de chave de criptografia de 1024, 2048 e 4096. São recomendados os comprimentos de chave de 2048 e superior.
    
- A compilação padrão ou a assinatura de hash, algoritmo é RSA. Os algoritmos de ECDH_P256, ECDH_P384 e ECDH_P521 também são suportados.
    
Portanto, há muito o que pensar e, definitivamente, há vários níveis de conforto com a solicitação de certificados de uma AC. Forneceremos mais orientações abaixo para tornar o planejamento o mais simples possível.
  
### <a name="certificates-for-your-internal-servers"></a>Certificados para seus servidores internos

Você precisará de certificados para a maioria dos seus servidores internos e, mais provavelmente, você os receberá de uma AC interna (que é uma localizada em seu domínio). Se quiser, você pode solicitar esses certificados de uma AC externa (uma localizada na Internet). Se você estiver se perguntando qual AC pública deve ir, confira a lista de [parceiros de certificados de comunicações unificadas](/SkypeForBusiness/certification/services-ssl) .
  
Você também precisará de certificados quando o Skype for Business Server 2015 se comunicar com outros aplicativos e servidores, como o Microsoft Exchange Server. Isso, obviamente, precisa ser um certificado que outros aplicativos e servidores podem usar de uma maneira suportada. O Skype for Business Server 2015 e outros produtos da Microsoft dão suporte ao protocolo de autorização aberta (OAuth) para autenticação e autorização de servidor para servidor. Se você estiver interessado nisso, temos um artigo de planejamento adicional para o OAuth e o Skype for Business Server 2015.
  
O Skype for Business Server 2015 também inclui suporte para (sem exigir) certificados assinados usando a função de hash de criptografia SHA-256. Para dar suporte ao acesso externo usando SHA-256, o certificado externo precisa ser emitido por uma autoridade de certificação pública usando SHA-256.
  
Para experimentar e manter as coisas diretas, colocamos os requisitos de certificado para servidores Standard Edition, pools de front-ends e outras funções, com o contoso.com fictício que está sendo usado para exemplos (provavelmente você está usando outra coisa para seu ambiente). Estes são todos os certificados de servidor Web padrão, com chaves privadas que não são exportáveis. Algumas coisas adicionais a serem observadas:
  
- O uso avançado de chave (EKU) do servidor é automaticamente configurado quando você usa o assistente de certificado para solicitar certificados.
    
- Cada nome amigável do certificado deve ser exclusivo no repositório do computador.
    
- De acordo com os exemplos de nomes abaixo, se você configurou o sipinternal.contoso.com ou o sipexternal.contoso.com no seu DNS, eles precisam ser adicionados ao nome alternativo da entidade (SAN) do certificado.
    
Certificados para servidores Standard Edition:
  
|**Certificado**|**Nome da entidade/nome comum**|**Nome alternativo da entidade**|**Exemplo**|**Comments**|
|:-----|:-----|:-----|:-----|:-----|
|Padrão  <br/> |FQDN do pool  <br/> |FQDN do pool e FQDN do servidor  <br/> Se você tiver vários domínios SIP e tiver habilitado a configuração automática do cliente, o assistente de certificados detectará e adicionará os FQDNs de cada domínio SIP aceito.  <br/> Se esse pool é o servidor de logon automático para clientes, e a combinação estrita do Sistema de Nome de Domínio (DNS) é exigida na política do grupo, também é preciso de entradas para o sip.sipdomain (para cada domínio de SIP que você tiver).  <br/> |SN = SE01. contoso. com; SAN = SE01. contoso. com  <br/> Se esse pool é o servidor de logon automático para clientes, e se a combinação estrita de DNS for exigida na política do grupo, também serão precisos: SAN=sip.contoso.com; SAN=sip.fabrikam.com  <br/> |Nos servidores Standard Edition Standard Edition Server, o FQDN do servidor é o mesmo que o FQDN do pool.  <br/> O assistente detecta quaisquer domínios SIP especificados durante a instalação e os adiciona automaticamente ao nome alternativo para a entidade.  <br/> Você também pode usar esse certificado para autenticação de servidor para servidor.  <br/> |
|Web interna  <br/> |FQDN do servidor  <br/> |Cada um dos seguintes:  <br/> • FQDN da Web interna (que é o mesmo que o FQDN do servidor)  <br/> E  <br/> • Atender a URLs simples  <br/> • URL simples discada  <br/> • URL simples de administração  <br/> OU  <br/> • Uma entrada curinga para URLs simples  <br/> |SN = SE01. contoso. com; SAN = SE01. contoso. com; SAN = reunião. contoso. com; SAN = atender. fabrikam. com; SAN = dialem. contoso. com; SAN = admin. contoso. com  <br/> Como usar um certificado curinga:  <br/> SN = SE01. contoso. com; SAN = SE01. contoso. com; SAN = \* . contoso.com  <br/> |Não é possível substituir o FQDN interno da Web no construtor de topologias.  <br/> Se você tiver vários URLs simples de reunião, você precisará incluir todos eles como SANs.  <br/> As entradas curinga são suportadas pelas entradas de URL simples.  <br/> |
|Web externa  <br/> |FQDN do servidor  <br/> |Cada um dos seguintes:  <br/> • FQDN da Web externa  <br/> E  <br/> • URL simples discada  <br/> • Atender a URLs simples por domínio SIP  <br/> OU  <br/> • Uma entrada curinga para URLs simples  <br/> |SN = SE01. contoso. com; SAN = webcon01. contoso. com; SAN = reunião. contoso. com; SAN = atender. fabrikam. com; SAN = dialem. contoso. com  <br/> Como usar um certificado coringa:  <br/> SN = SE01. contoso. com; SAN = webcon01. contoso. com; SAN = \* . contoso.com  <br/> |Se você tiver vários URLs simples de reunião, será necessário incluir todos eles como nomes alternativos de entidade.  <br/> As entradas curinga são suportadas pelas entradas de URL simples.  <br/> |
   
Certificados para servidores front-end em um pool de front-ends:
  
|**Certificado**|**Nome da entidade/nome comum**|**Nome alternativo da entidade**|**Exemplo**|**Comments**|
|:-----|:-----|:-----|:-----|:-----|
|Padrão  <br/> |FQDN do pool  <br/> |FQDN do pool e FQDN do servidor  <br/> Se você tiver vários domínios SIP e tiver habilitado a configuração automática do cliente, o assistente de certificados detectará e adicionará os FQDNs de cada domínio SIP aceito.  <br/> Se esse pool é o servidor de logon automático para clientes, e a combinação estrita do Sistema de Nome de Domínio (DNS) é exigida na política do grupo, também é preciso de entradas para o sip.sipdomain (para cada domínio de SIP que você tiver).  <br/> |SN = EEpool. contoso. com; SAN = EEpool. contoso. com; SAN = ee01. contoso. com  <br/> Se esse pool é o servidor de logon automático para clientes, e se a combinação estrita de DNS for exigida na política do grupo, também serão precisos: SAN=sip.contoso.com; SAN=sip.fabrikam.com  <br/> |O assistente detecta quaisquer domínios SIP especificados durante a instalação e os adiciona automaticamente ao nome alternativo para a entidade.  <br/> Você também pode usar esse certificado para autenticação de servidor para servidor.  <br/> |
|Web interna  <br/> |FQDN do pool  <br/> |Cada um dos seguintes:  <br/> • FQDN da Web interna (que não é o mesmo que o FQDN do servidor)  <br/> • FQDN do servidor  <br/> • FQDN do pool do Skype for Business  <br/> E  <br/> • Atender a URLs simples  <br/> • URL simples discada  <br/> • URL simples de administração  <br/> OU  <br/> • Uma entrada curinga para URLs simples  <br/> |SN = ee01. contoso. com; SAN = ee01. contoso. com; SAN = reunião. contoso. com; SAN = atender. fabrikam. com; SAN = dialem. contoso. com; SAN = admin. contoso. com  <br/> Como usar um certificado curinga:  <br/> SN = ee01. contoso. com; SAN = ee01. contoso. com; SAN = \* . contoso.com  <br/> |Se você tiver vários URLs simples de reunião, será necessário incluir todos eles como nomes alternativos de entidade.  <br/> As entradas curinga são suportadas pelas entradas de URL simples.  <br/> |
|Web externa  <br/> |FQDN do pool  <br/> |Cada um dos seguintes:  <br/> • FQDN da Web externa  <br/> E  <br/> • URL simples discada  <br/> • URL simples de administração  <br/> OU  <br/> • Uma entrada curinga para URLs simples  <br/> |SN = ee01. contoso. com; SAN = webcon01. contoso. com; SAN = reunião. contoso. com; SAN = atender. fabrikam. com; SAN = dialem. contoso. com  <br/> Como usar um certificado curinga:  <br/> SN = ee01. contoso. com; SAN = webcon01. contoso. com; SAN = \* . contoso.com  <br/> |Se você tiver vários URLs simples de reunião, será necessário incluir todos eles como nomes alternativos de entidade.  <br/> As entradas curinga são suportadas pelas entradas de URL simples.  <br/> |
   
Certificados para o diretor:
  
|**Certificado**|**Nome da entidade/nome comum**|**Nome alternativo da entidade**|**Exemplo**|
|:-----|:-----|:-----|:-----|
|Padrão  <br/> |Director pool  <br/> |FQDN do diretor, FQDN do pool de diretores.  <br/> Se esse pool for o servidor de logon automático para clientes e a correspondência de DNS estrita for necessária na política de grupo, você também precisará de entradas para SIP. sipdomain (para cada domínio SIP que você tiver).  <br/> |pool.contoso.com; SAN = dir01. contoso. com  <br/> Se esse pool de Diretor for o servidor de logon automático para clientes, e se a combinação estrita de DNS for exigida na política do grupo, também serão precisos: SAN=sip.contoso.com; SAN=sip.fabrikam.com  <br/> |
|Web interna  <br/> |FQDN do servidor  <br/> |Cada um dos seguintes:  <br/> • FQDN da Web interna (que é o mesmo que o FQDN do servidor)  <br/> • FQDN do servidor  <br/> • FQDN do pool do Skype for Business  <br/> E  <br/> • Atender a URLs simples  <br/> • URL simples discada  <br/> • URL simples de administração  <br/> OU  <br/> • Uma entrada curinga para URLs simples  <br/> |SN = dir01. contoso. com; SAN = dir01. contoso. com; SAN = reunião. contoso. com; SAN = atender. fabrikam. com; SAN = dialem. contoso. com; SAN = admin. contoso. com  <br/> Como usar um certificado curinga:  <br/> SN = dir01. contoso. com; SAN = dir01. contoso. com SAN = \* . contoso.com  <br/> |
|Web externa  <br/> |FQDN do servidor  <br/> |Cada um dos seguintes:  <br/> • FQDN da Web externa  <br/> E  <br/> • Atender a URLs simples por domínio SIP  <br/> • URL simples discada  <br/> OU  <br/> • Uma entrada curinga para URLs simples  <br/> |O FQDN da Web externa do diretor deve ser diferente do pool de front-ends ou servidor front-end.  <br/> SN = dir01. contoso. com; SAN = directorwebcon01. contoso. com SAN = encontro. contoso. com; SAN = atender. fabrikam. com; SAN = dialem. contoso. com  <br/> Como usar um certificado curinga:  <br/> SN = dir01. contoso. com; SAN = directorwebcon01. contoso. com SAN = \* . contoso.com  <br/> |
   
Certificados para servidor de mediação autônomo:
  
|**Certificado**|**Nome da entidade/nome comum**|**Nome alternativo da entidade**|**Exemplo**|
|:-----|:-----|:-----|:-----|
|Padrão  <br/> |FQDN do pool  <br/> |FQDN do pool  <br/> FQDN do servidor membro do pool  <br/> |SN = medsvr-pool.contoso.net; SAN = medsvr-pool.contoso.net; SAN = medsvr01. contoso. net  <br/> |
   
Certificados para aparelho de filial persistente:
  
|**Certificado**|**Nome da entidade/nome comum**|**Nome alternativo da entidade**|**Exemplo**|
|:-----|:-----|:-----|:-----|
|Padrão  <br/> |FQDN do aplicativo  <br/> |SIP. \< sipdomain \> (você precisa apenas de uma entrada por domínio SIP)  <br/> |SN = sba01. contoso. net; SAN = SIP. contoso. com; SAN = SIP. fabrikam. com  <br/> |
   
### <a name="certificates-for-your-persistent-chat-server"></a>Certificados para seu servidor de chat persistente

Ao instalar seu servidor de chat persistente, você precisará de um certificado emitido pela mesma autoridade de certificação usada pelos servidores internos do Skype for Business Server 2015. Isso precisa ser feito para cada servidor que executa os serviços Web de chat persistente para upload/download de arquivos. É altamente recomendável que você tenha os certificados necessários antes de iniciar sua instalação de chat persistente, e se sua autoridade de certificação for externa, até mesmo mais para (essas coisas podem levar algum tempo para serem emitidas).
  
### <a name="certificates-for-external-user-access-edge"></a>Certificados para acesso de usuário externo (borda)

O Skype for Business Server 2015 suporta o uso de um **único certificado público** para interfaces externas de borda de acesso e webconferência, além do serviço de autenticação a/V, que é fornecido através dos servidores de borda. A interface interna de borda normalmente usará um certificado privado emitido pela autoridade de certificação interna, mas se preferir, você também poderá usar um certificado público para isso, caso seja proveniente de uma autoridade de certificação confiável.
  
Seu proxy reverso (RP) também usará um certificado público e criptografará a comunicação do seu RP para os clientes e o RP para servidores internos usando HTTP (ou mais precisamente, TLS sobre HTTP).
  
### <a name="certificates-for-mobility"></a>Certificados para mobilidade

Se você estiver implantando a mobilidade e estiver oferecendo suporte à descoberta automática para clientes móveis, será necessário incluir algumas entradas de nome alternativo de entidade adicional nos seus certificados para dar suporte a conexões seguras dos clientes móveis.
  
Quais certificados? Você precisará de nomes SAN para descoberta automática nos certificados aqui:
  
- Director pool
    
- Pool de Front-Ends
    
- Proxy reverso
    
Listaremos as especificações de cada tabela abaixo.
  
Agora, é aí que um pouco de planejamento é bom, mas, às vezes, você implantou o Skype for Business Server 2015 sem a intenção de implantar a mobilidade, e isso é feito na linha quando você já tem certificados no ambiente. A reemissão deles por meio de uma autoridade de certificação interna normalmente é muito fácil, mas com certificados públicos de uma AC pública, que pode ser um pouco mais caro.
  
Se for o que você está procurando e se você tiver muitos domínios SIP (o que tornaria a adição de SANS mais caras), poderá configurar seu proxy reverso para usar HTTP para a solicitação de serviço de descoberta automática inicial, em vez de usar HTTPS (que é a configuração padrão). O tópico Planejamento para mobilidade tem mais informações sobre isso.
  
Requisitos de certificado de pool de front-end e pool de diretores:
  
|**Descrição**|**Entrada de SAN**|
|:-----|:-----|
|URL interna do serviço de descoberta automática  <br/> |SAN = lyncdiscoverinternal. \< sipdomain\>  <br/> |
|URL externa do serviço de descoberta automática  <br/> |SAN = lyncdiscover. \< sipdomain\>  <br/> |
   
Como alternativa, você pode usar SAN = \* . \< sipdomain\>
  
Requisitos de certificado de proxy reverso (AC pública):
  
|**Descrição**|**Entrada de SAN**|
|:-----|:-----|
|URL externa do serviço de descoberta automática  <br/> |SAN = lyncdiscover. \< sipdomain\>  <br/> |
   
Essa SAN precisa ser atribuída ao certificado atribuído ao ouvinte SSL em seu proxy reverso.
  
> [!NOTE]
> Seu ouvinte de proxy reverso terá SANs para seus URLs de serviços Web externos. Alguns exemplos seriam SAN = skypewebextpool01. contoso. com e dirwebexternal.contoso.com, se você tiver implantado o diretor (opcional). 
  
## <a name="file-share"></a>Compartilhamento de arquivo
<a name="Fileshare"> </a>

O Skype for Business Server 2015 pode usar o mesmo compartilhamento de arquivo para todo o armazenamento de arquivos. Você precisa ter em mente o seguinte:
  
- Um compartilhamento de arquivos precisa estar em um (armazenamento de conexão direta) ou em uma rede de área de armazenamento (SAN), e isso inclui o sistema de arquivos distribuído (DFS), bem como uma matriz redundante de discos independentes (RAID) para repositórios de arquivos. Para ler mais sobre o DFS no Windows Server 2012, confira [esta página DFS](https://technet.microsoft.com/library/jj127250.aspx).
    
- Recomendamos um cluster compartilhado para o compartilhamento de arquivos. Se você estiver usando um, deverá usar um cluster do Windows Server 2012 ou Windows Server 2012 R2. O Windows Server 2008 R2 também é aceitável. Por que a versão mais recente do Windows? Versões mais antigas podem não ter as permissões corretas para habilitar todos os recursos. Você pode usar o administrador de cluster para criar os compartilhamentos de arquivos e este tutorial [sobre como criar compartilhamentos de arquivo em um](https://support.microsoft.com/help/224967/how-to-create-file-shares-on-a-cluster) artigo de cluster o ajudará com esses detalhes.
    
> [!CAUTION] 
> Você deve saber que usar o NAS (armazenamento conectado à rede) como um compartilhamento de arquivos não é suportado, portanto, use uma das opções listadas acima. 
  
