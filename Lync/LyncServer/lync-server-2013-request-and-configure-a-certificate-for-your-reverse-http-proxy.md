---
title: Solicitar e configurar um certificado para seu proxy HTTP reverso
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Request and configure a certificate for your reverse HTTP proxy
ms:assetid: 4b70991e-5f10-40a3-b069-0b227c3a3a0a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg429704(v=OCS.15)
ms:contentKeyID: 48184085
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2597bf31c9f0cc9f4316f505811426f2c9948a6f
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41723842"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="request-and-configure-a-certificate-for-your-reverse-http-proxy-in-lync-server-2013"></a>Solicitar e configurar um certificado para seu proxy HTTP reverso no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2014-02-14_

Você precisa instalar o certificado de autoridade de certificação (CA) raiz no servidor que executa o Microsoft Forefront Threat Management Gateway 2010 ou o IIS ARR para a infraestrutura da CA que emitiu os certificados do servidor para os servidores internos que executam o Microsoft Lync Server 2013.

Você também deve instalar um certificado de servidor Web público em seu servidor proxy reverso. Os nomes alternativos da entidade deste certificado devem conter os nomes de domínio totalmente qualificados externos (FQDNs) publicados de cada pool que seja home para os usuários habilitados para acesso remoto e os FQDNs externos de todos os diretores ou pools de directors que serão usados dentro Essa infraestrutura de borda. O nome alternativo do assunto também deve conter a URL simples da reunião, a URL simples discada e, se você estiver implantando aplicativos móveis e planejar usar a descoberta automática, a URL do serviço de descoberta automática externa, conforme mostrado na tabela a seguir.


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th></th>
<th>Valor</th>
<th>Exemplo</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Nome do assunto</p></td>
<td><p>FQDN do pool</p></td>
<td><p>webext.contoso.com</p></td>
</tr>
<tr class="even">
<td><p>Nome alternativo de entidade</p></td>
<td><p>FQDN do pool</p></td>
<td><p>webext.contoso.com</p>



> [!IMPORTANT]
> O nome do requerente também deve estar presente no nome alternativo do assunto.

</td>
</tr>
<tr class="odd">
<td><p>Nome alternativo de entidade</p></td>
<td><p>Serviços Web de director opcionais (se o diretor for implantado)</p></td>
<td><p>webdirext.contoso.com</p></td>
</tr>
<tr class="even">
<td><p>Nome alternativo de entidade</p></td>
<td><p>URL simples de reunião</p>



> [!NOTE]
> Todas as URLs simples de reunião devem estar no nome alternativo da entidade. Cada domínio SIP deve ter pelo menos uma URL simples de reunião ativa.

</td>
<td><p>meet.contoso.com</p></td>
</tr>
<tr class="odd">
<td><p>Nome alternativo de entidade</p></td>
<td><p>URL simples de discagem</p></td>
<td><p>dialin.contoso.com</p></td>
</tr>
<tr class="even">
<td><p>Nome alternativo de entidade</p></td>
<td><p>Servidor Office Web Apps</p></td>
<td><p>officewebapps01.contoso.com</p></td>
</tr>
<tr class="odd">
<td><p>Nome alternativo de entidade</p></td>
<td><p>URL do serviço de descoberta automática externo</p></td>
<td><p>lyncdiscover.contoso.com</p>



> [!NOTE]
> Se você também estiver usando o Microsoft Exchange Server, também precisará configurar regras de proxy reverso para as URLs de serviços Web e descoberta automática do Exchange.

</td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]
> Se a sua implantação interna consistir em mais de um servidor Standard Edition ou pool de front-end, você precisará configurar regras de publicação na Web para cada FQDN do Web farm externo e será necessário um ouvinte de certificado e Web para cada um, ou você deve obter um certificado cujo nome alternativo para o assunto contém os nomes usados por todos os grupos, atribua-os a um ouvinte da Web e compartilhe-os entre várias regras de publicação na Web.



</div>

<div>

## <a name="create-a-certificate-request"></a>Criar uma solicitação de certificado

Crie uma solicitação de certificado no proxy reverso. Você cria uma solicitação em outro computador, mas deve exportar o certificado assinado com a chave privada e importá-lo para o proxy inverso após tê-lo recebido da autoridade de certificação pública.

<div>


> [!NOTE]
> Uma solicitação de certificado ou um CSR (solicitação de assinatura de certificado) é uma solicitação para uma autoridade de certificação pública (CA) confiável para validar e assinar a chave pública do computador solicitante. Quando um certificado é gerado, uma chave pública e uma chave privada são criadas. Somente a chave pública é compartilhada e assinada. Como o nome indica, a chave pública é disponibilizada para qualquer solicitação Pública. A chave pública é usada por clientes, servidores e outros solicitantes que precisam trocar informações com segurança e validar a identidade do computador. A chave privada é mantida protegida e é usada somente pelo computador que criou o par de chaves para descriptografar mensagens criptografadas com sua chave pública. A chave privada pode ser usada para outras finalidades. Para fins de proxy reverso, a codificação de dados é o uso principal. O secondarily, a autenticação de certificado no nível da chave do certificado, é limitado apenas à validação de que um solicitante tem a chave pública do computador ou de que o computador com o qual você tem uma chave pública é realmente o computador que ele alega ser.



</div>

<div>


> [!TIP]
> Se você planejar os certificados do servidor de borda e os certificados de proxy inversos ao mesmo tempo, observe que há uma excelente semelhança entre os dois requisitos de certificado. Ao configurar e solicitar o certificado do servidor de borda, combine o servidor de borda e os nomes alternativos de entidades de proxy reverso. Você pode usar o mesmo certificado para seu proxy reverso se exportar o certificado e a chave privada e copiar o arquivo exportado para o proxy reverso e, em seguida, importar o par de certificados/chaves e atribuí-lo conforme necessário nos procedimentos futuros. Consulte os requisitos de certificado para o plano do&nbsp;servidor de borda<A href="lync-server-2013-plan-for-edge-server-certificates.md">para certificados do servidor de borda no Lync Server 2013</A> e o resumo de certificado de proxy reverso <A href="lync-server-2013-certificate-summary-reverse-proxy.md">-proxy reverso no Lync Server 2013</A>. Certifique-se de criar o certificado com uma chave privada exportável. A criação do certificado e da solicitação de certificado com uma chave privada exportável é necessária para servidores de borda em pool, portanto, isso é uma prática normal e o assistente de certificado no assistente de implantação do Lync Server para o servidor de borda permite que você defina o sinalizador <STRONG>criar chave privada exportável</STRONG> . Depois de receber a solicitação de certificado de volta da autoridade de certificação pública, você exportará o certificado e a chave privada. Consulte a seção "para exportar o certificado com a chave privada para servidores de borda em um pool" no tópico <A href="lync-server-2013-set-up-certificates-for-the-external-edge-interface.md">configurar certificados para a interface de borda externa do Lync Server 2013</A> para obter detalhes sobre como criar e exportar seu certificado com uma chave privada. A extensão do certificado deve ser do tipo <STRONG>. pfx</STRONG>.



</div>

Para gerar uma solicitação de assinatura de certificado no computador em que o certificado e a chave privada serão atribuídos, faça o seguinte:

**Criando uma solicitação de assinatura de certificado**

1.  Abra o console de gerenciamento Microsoft (MMC) e adicione o snap-in de certificados e selecione **computadores**e, em seguida, expanda **pessoal**. Para obter detalhes sobre como criar um console de certificados no console de gerenciamento Microsoft (MMC), [http://go.microsoft.com/fwlink/?LinkId=282616](http://go.microsoft.com/fwlink/?linkid=282616)consulte.

2.  Clique com o botão direito do mouse em **certificados**, clique em **todas as tarefas**, clique em **operações avançadas**, clique em **criar solicitação personalizada**.

3.  Na página **registro de certificado** , clique em **Avançar**.

4.  Na página **selecionar política de registro de certificado** em **solicitação personalizada**, selecione **continuar sem política de registro**. Click **Next**.

5.  Na página **solicitação personalizada** , em **modelo** , selecione **(nenhum modelo) chave herdada**. A menos que seja direcionado de outra forma pelo seu provedor de certificado, deixe a opção **suprimir extensões padrão** desmarcada e a seleção de **formato de solicitação** em ** \#PKCS 10**. Click **Next**.

6.  Na página **informações do certificado** , clique em **detalhes**e, em seguida, clique em **Propriedades**.

7.  Na página **Propriedades do certificado** , na guia **geral** , no campo **nome amigável** , digite um nome para este certificado. Opcionalmente, digite uma descrição no campo **Descrição** . O nome amigável e a descrição geralmente são usados pelo administrador para identificar qual é a finalidade do certificado, como **ouvinte de proxy reverso para o Lync Server**.

8.  Selecione a guia **assunto** . Em **nome do assunto** do **tipo**, selecione **nome comum** para o tipo de nome do assunto. Para o **valor**, digite o nome do requerente que você usará para o proxy reverso e clique em **Adicionar**. No exemplo fornecido na tabela deste tópico, o nome do assunto é webext.contoso.com e seria digitado no campo valor para o nome do assunto.

9.  Na guia **assunto** em **nome alternativo**, selecione **DNS** na lista suspensa para o **tipo**. Para cada nome alternativo de assunto definido que você precisa no certificado, digite o nome de domínio totalmente qualificado e clique em **Adicionar**. Por exemplo, na tabela, há três nomes alternativos de entidades, meet.contoso.com, dialin.contoso.com e lyncdiscover.contoso.com. No campo **valor** , digite Meet.contoso.com e, em seguida, clique em **Adicionar**. Repita para cada assunto nomes alternativos que você precisa definir.

10. Na página **Propriedades do certificado** , clique na guia **extensões** . Nesta página, você definirá os objetivos da chave criptográfica em **uso da chave** e o uso estendido da chave em **uso estendido da chave (políticas de aplicativo)**.

11. Clique na seta **uso da chave** para mostrar as **opções disponíveis**. Em opções disponíveis, clique em **assinatura digital**e, em seguida, clique em **Adicionar**. Clique em **codificação de chave**e, em seguida, clique em **Adicionar**. Se a caixa de seleção **fazer com que esses usos de chave críticos** estiver desmarcada, marque a caixa de seleção.

12. Clique na seta **uso estendido da chave (políticas do aplicativo)** para mostrar as **opções disponíveis**. Em opções disponíveis, clique em **autenticação do servidor**e, em seguida, clique em **Adicionar**. Clique em **autenticação do cliente**e, em seguida, clique em **Adicionar**. Se a caixa de seleção para fazer com que **os usos da chave estendida** forem marcada, desmarque a caixa de seleção. Ao contrário da caixa de seleção uso da chave (que deve ser marcada), você deve ter certeza de que a caixa de seleção uso estendido da chave não está marcada.

13. Na página **Propriedades do certificado** , clique na guia **chave privada** . Clique na seta **Opções de tecla** . Em **tamanho da chave**, selecione **2048** na lista suspensa. Se você estiver gerando este par de chaves e o CSR em um computador diferente do proxy inverso ao qual esse certificado se destina, selecione **tornar a chave privada exportável**.
    
    <div>
    
    <table>
    <thead>
    <tr class="header">
    <th><img src="images/Gg398321.security(OCS.15).gif" title="segurança" alt="security" />Observação de segurança:</th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td>Selecionar <strong>tornar uma chave privada exportável</strong> geralmente é avisado quando você tem mais de um proxy reverso em um farm, pois você copiará o certificado e a chave privada para cada máquina no farm. Se você permitir uma chave privada exportável, deve tomar cuidado com o certificado e o computador em que ele é gerado. A chave privada, se comprometida, tornará o certificado inútil, bem como exporá potencialmente o computador ou computadores a acesso externo e outras vulnerabilidades de segurança.</td>
    </tr>
    </tbody>
    </table>
    
    </div>

14. Na guia **chave privada** , clique na seta **tipo de chave** . Selecione a opção **Exchange** .

15. Clique em **OK** para salvar as **Propriedades de certificado** que você definiu.

16. Na página **registro de certificado** , clique em **Avançar**.

17. Na página **onde você deseja salvar a solicitação offline?** , você será solicitado a fornecer um **nome de arquivo** e um formato de **arquivo** para salvar a solicitação de assinatura de certificado.

18. No campo de entrada **nome do arquivo** , digite um caminho e um nome de arquivo para a solicitação ou clique em **procurar** para selecionar um local para o arquivo e digite o nome do arquivo para a solicitação.

19. Em **formato de arquivo**, clique em **base 64** ou **binário**. Selecione **Base 64** , a menos que você seja instruído de outra forma pelo fornecedor dos seus certificados.

20. Localize o arquivo de solicitação que você salvou na etapa anterior. Envie à sua autoridade de certificação pública.
    
    <div>
    

    > [!IMPORTANT]
    > A Microsoft identificou CAs públicas que atendem aos requisitos para fins de comunicação unificada. Uma lista é mantida no seguinte artigo da base de dados de conhecimento. <A href="http://go.microsoft.com/fwlink/?linkid=282625">http://go.microsoft.com/fwlink/?LinkId=282625</A>

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

