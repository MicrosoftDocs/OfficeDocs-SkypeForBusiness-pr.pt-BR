---
title: 'Lync Server 2013: Configurando políticas de inicialização do cliente'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configuring client bootstrapping policies
ms:assetid: 45042eca-b845-4207-b12f-b8b7f5d44bdf
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425941(v=OCS.15)
ms:contentKeyID: 48184031
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 06119d5488b47adfe01a934aca9a55581feaf33e
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34836288"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-client-bootstrapping-policies-in-lync-server-2013"></a>Configurando as políticas de inicialização do cliente no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2013-02-21_

O Console de Gerenciamento de Política de Grupo (GPMC) e o Editor de Objeto de Política de Grupo são ferramentas que você utiliza para gerenciar Políticas de Grupo. Incluído no modelo administrativo da política de grupo do Office há modelos administrativos do Lync 2013. admx (ADMX) e. adml (ADML), que contêm as configurações de política baseadas no registro que você configura para objetos de política de grupo no domínio. Os arquivos ADML são complementos específicos de idioma para arquivos ADMX. Cada arquivo ADMX e ADML contém as configurações de política para um único aplicativo do Office. Para obter mais informações, consulte "arquivos de modelo administrativo do Office 2013 (ADMX, ADML)" na documentação do <http://go.microsoft.com/fwlink/p/?linkid=267516>Office 2013 em.

Para o Lync 2013, há várias políticas de inicialização do cliente que você deve considerar Configurando antes de os usuários entrarem no servidor pela primeira vez. Por exemplo, os servidores padrão e o modo de segurança que o cliente deve utilizar até que a entrada esteja concluída. Você pode usar uma Política de Grupo para estabelecer essas configurações nos Registros dos computadores dos usuários antes que eles entrem e comecem a receber configurações de provisionamento em banda do servidor. A tabela a seguir lista as configurações de política de grupo que estão disponíveis para o Lync 2013.

### <a name="group-policy-settings-for-lync-2013"></a>Configurações da política de grupo para o Lync 2013

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Configuração de Política de Grupo</th>
<th>Descrição</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Especificar servidor<br />
(ConfigurationMode)</p></td>
<td><p>Especifica como o Lync 2013 identifica o transporte e o servidor a serem usados durante a entrada. Com essa configuração, você especifica o seguinte:</p>
<ul>
<li><p>ServerAddressExternal: Especifica o nome de servidor ou endereço IP utilizado pelos clientes e contatos federados ao se conectar de fora do firewall externo.</p></li>
<li><p>ServerAddressInternal: Especifica o nome de servidor ou endereço IP utilizado quando os clientes se conectam de dentro do firewall da organização.</p></li>
<li><p>Transport: Especifica o protocolo TCP ou protocolo TLS.</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p>Versões adicionais do servidor com suporte<br />
(ConfiguredServerCheckValues)</p></td>
<td><p>Especifica uma lista de nomes de versão do servidor separados por ponto-e-vírgulas nos quais o Lync Server 2013 fará logon, além das versões do servidor com suporte por padrão.</p></td>
</tr>
<tr class="odd">
<td><p>Desativa o upload automático de logs de falha de assinatura (DisableAutomaticSendTracing)</p></td>
<td><p>Carrega automaticamente os logs de falha de entrada no Lync Server para análise. Nenhum log será carregado automaticamente se a entrada ocorrer com êxito. Se essa política não estiver configurada, ocorrerá o seguinte:</p>
<dl>
<dt><span></span></dt>
<dd><p>Para usuários do Lync Online: logs de falha de entrada são carregados automaticamente.</p>
</dd>
<dt><span></span></dt>
<dd><p>Para usuários do Lync local: uma caixa de diálogo de confirmação é exibida para o usuário antes do carregamento.</p>
</dd>
</dl>
<p>Quando essa configuração estiver desabilitada, os logs de entrada serão carregados automaticamente para o servidor do Lync para os usuários do Lync local e do Lync Online. Quando essa configuração é habilitada, os logs de entrada nunca são carregados automaticamente.</p></td>
</tr>
<tr class="even">
<td><p>Desabilitar o fallback de HTTP para conexão SIP<br />
(DisableHttpConnect)</p></td>
<td><p>Impede que o Lync Server tente se conectar ao servidor usando HTTP, se TLS ou TCP não estiverem disponíveis. Por padrão, o Lync tenta primeiro se conectar ao servidor usando TLS ou TCP e, se nenhum desses métodos de transporte for bem-sucedido, o Lync tenta se conectar usando HTTP. Use essa política para desabilitar a tentativa de conexão por HTTP de fallback.</p></td>
</tr>
<tr class="odd">
<td><p>Exigir credenciais de logon<br />
(DisableNTCredentials)</p></td>
<td><p>Requer que o usuário forneça credenciais de logon para o Lync em vez de usar as credenciais do Windows automaticamente durante a entrada em um servidor SIP.</p></td>
</tr>
<tr class="even">
<td><p>Desabilitar a verificação de versão do servidor<br />
(DisableServerCheck)</p></td>
<td><p>Se você definir essa política como 1, o Lync não verifica o nome e a versão do servidor antes de entrar. Por padrão, o Lync faz essas verificações antes de entrar.</p></td>
</tr>
<tr class="odd">
<td><p>Habilitar o uso do BITS para baixar arquivos do serviço de catálogo de endereços<br />
(EnableBitsForGalDownload)</p></td>
<td><p>Permite que o Lync use o serviço de transferência inteligente em segundo plano (BITS) para baixar os arquivos dos serviços de catálogo de endereços.</p></td>
</tr>
<tr class="even">
<td><p>Configurar o modo de segurança SIP<br />
(EnableSIPHighSecurityMode)</p></td>
<td><p>Permite que o Lync envie e receba mensagens de chat com mais segurança. Essa política não tem efeito no Windows .NET, nem em serviços de Servidor do Microsoft Exchange.</p>
<p>Se você não definir essa configuração de política, o Lync poderá usar qualquer transporte. Mas se ele não usar TLS e se o servidor autenticar usuários, o Lync deverá usar a autenticação NTLM ou Kerberos.</p></td>
</tr>
<tr class="odd">
<td><p>Atraso inicial do download do catálogo de endereços global<br />
(GalDownloadInitialDelay)</p></td>
<td><p>Especifica o período de tempo antes de um download da lista de endereço global (GAL) ocorrer. O valor padrão é 60 minutos, o que significa que o download do arquivo GAL é atrasado para um período aleatório entre 0 e 60 minutos.</p></td>
</tr>
<tr class="even">
<td><p>Impedir que os usuários executem o Microsoft Lync<br />
(PreventRun)</p></td>
<td><p>Impede que os usuários executem o Lync. Você pode definir essa configuração de política na Configuração do Computador e na Configuração do Usuário, mas a configuração de política na Configuração do Computador tem precedência.</p></td>
</tr>
<tr class="odd">
<td><p>Permitir armazenamento de senhas de usuários<br />
(SavePassword)</p></td>
<td><p>Permite que o Lync armazene senhas.</p></td>
</tr>
<tr class="even">
<td><p>Configurar o modo de compactação SIP<br />
(SipCompression)</p></td>
<td><p>Especifica quando ativar a compressão do SIP. Por padrão, a compressão do SIP está ativada com base na velocidade do adaptador. Observe que configurar tal política pode causar um aumento no tempo de assinatura.</p></td>
</tr>
<tr class="odd">
<td><p>Lista de domínios confiáveis<br />
TrustModelData</p></td>
<td><p>Lista os domínios confiáveis que não correspondem ao prefixo do domínio SIP cliente.</p></td>
</tr>
</tbody>
</table>


As políticas configuradas no servidor têm precedência sobre as configurações de Política de Grupo e as opções de cliente configuradas pelo usuário. A tabela a seguir resume a ordem na qual as configurações têm precedência quando ocorre um conflito.

### <a name="group-policy-precedence"></a>Precedência das Políticas de Grupo

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Precedência</th>
<th>Local ou método da configuração</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>1</p></td>
<td><p>Provisionamento em banda do Lync Server 2013</p></td>
</tr>
<tr class="even">
<td><p>2</p></td>
<td><p>HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\Office\15.0\Lync</p></td>
</tr>
<tr class="odd">
<td><p>3</p></td>
<td><p>HKEY_CURRENT_USER\SOFTWARE\Policies\Microsoft\Office\15.0\Lync</p></td>
</tr>
<tr class="even">
<td><p>4</p></td>
<td><p>A caixa de diálogo Lync-opções no Lync 2013</p></td>
</tr>
</tbody>
</table>


<div>

## <a name="to-define-group-policy-settings-by-using-the-lync-2013-administrative-template-files"></a>Para definir configurações de política de grupo usando os arquivos de modelo administrativo do Lync 2013

1.  Crie uma pasta de nível de raiz para inserir todos os arquivos ADMX de idioma neutro. Por exemplo, crie uma pasta raiz para o armazenamento central no controlador de domínio neste local:
    
    `%systemroot%\sysvol\domain\policies\PolicyDefinitions`
    
    <div>
    

    > [!NOTE]  
    > Este procedimento presume que você deseja gerenciar diversos computadores no seu domínio. Neste caso, armazene os modelos em um repositório central na pasta Sysvol no controlador de domínio primário. Isso fornece uma localização de armazenamento central replicado para Modelos Administrativos.

    
    </div>

2.  Crie uma subpasta para cada idioma que for utilizar. Essas subpastas vão conter os arquivos de recurso ADML específicos do idioma. Por exemplo, crie uma subpasta para United States English (EN-US) neste local:
    
    `%systemroot%\sysvol\domain\policies\PolicyDefinitions\EN-US`

</div>

</div>

<span> </span>

</div>

</div>

</div>

