### <a name="wpf-datatemplate-elements-are-now-visible-to-uia"></a><span data-ttu-id="c4516-101">Los elementos DataTemplate de WPF ahora son visibles en la UIA</span><span class="sxs-lookup"><span data-stu-id="c4516-101">WPF DataTemplate elements are now visible to UIA</span></span>

|   |   |
|---|---|
|<span data-ttu-id="c4516-102">Detalles</span><span class="sxs-lookup"><span data-stu-id="c4516-102">Details</span></span>|<span data-ttu-id="c4516-103">Anteriormente, los elementos <xref:System.Windows.DataTemplate?displayProperty=name> no eran visibles para la automatización de la interfaz de usuario.</span><span class="sxs-lookup"><span data-stu-id="c4516-103">Previously, <xref:System.Windows.DataTemplate?displayProperty=name> elements were invisible to UI Automation.</span></span> <span data-ttu-id="c4516-104">A partir de la versión 4.5, la automatización de la IU detectará estos elementos.</span><span class="sxs-lookup"><span data-stu-id="c4516-104">Beginning in 4.5, UI Automation will detect these elements.</span></span> <span data-ttu-id="c4516-105">Esto resulta útil en muchos casos, pero puede interrumpir las pruebas que dependan de árboles de la UIA que no contengan elementos <xref:System.Windows.DataTemplate?displayProperty=name>.</span><span class="sxs-lookup"><span data-stu-id="c4516-105">This is useful in many cases, but can break tests that depend on UIA trees not containing <xref:System.Windows.DataTemplate?displayProperty=name> elements.</span></span>|
|<span data-ttu-id="c4516-106">Sugerencia</span><span class="sxs-lookup"><span data-stu-id="c4516-106">Suggestion</span></span>|<span data-ttu-id="c4516-107">Puede ser necesario actualizar las pruebas de automatización de la interfaz de usuario para esta aplicación con el fin de procesar el árbol de la UIA que ahora incluye elementos <xref:System.Windows.DataTemplate?displayProperty=name> que antes no eran visibles.</span><span class="sxs-lookup"><span data-stu-id="c4516-107">UI Automation tests for this app may need updated to account for the UIA tree now including previously invisible <xref:System.Windows.DataTemplate?displayProperty=name> elements.</span></span> <span data-ttu-id="c4516-108">Por ejemplo, en aquellas pruebas en las que se espere que haya ciertos elementos contiguos entre sí, ahora puede ser necesario esperar ciertos elementos intermedios de la UIA que antes no eran visibles.</span><span class="sxs-lookup"><span data-stu-id="c4516-108">For example, tests that expect some elements to be next to each other may now need to expect previously invisible UIA elements in between.</span></span> <span data-ttu-id="c4516-109">También puede ser necesario actualizar con nuevos valores pruebas que dependan de ciertos recuentos o índices para elementos de la UIA.</span><span class="sxs-lookup"><span data-stu-id="c4516-109">Or tests that rely on certain counts or indexes for UIA elements may need updated with new values.</span></span>|
|<span data-ttu-id="c4516-110">Ámbito</span><span class="sxs-lookup"><span data-stu-id="c4516-110">Scope</span></span>|<span data-ttu-id="c4516-111">Borde</span><span class="sxs-lookup"><span data-stu-id="c4516-111">Edge</span></span>|
|<span data-ttu-id="c4516-112">Versión</span><span class="sxs-lookup"><span data-stu-id="c4516-112">Version</span></span>|<span data-ttu-id="c4516-113">4.5</span><span class="sxs-lookup"><span data-stu-id="c4516-113">4.5</span></span>|
|<span data-ttu-id="c4516-114">Tipo</span><span class="sxs-lookup"><span data-stu-id="c4516-114">Type</span></span>|<span data-ttu-id="c4516-115">Tiempo de ejecución</span><span class="sxs-lookup"><span data-stu-id="c4516-115">Runtime</span></span>|
|<span data-ttu-id="c4516-116">API afectadas</span><span class="sxs-lookup"><span data-stu-id="c4516-116">Affected APIs</span></span>|<ul><li><xref:System.Windows.DataTemplate.%23ctor?displayProperty=nameWithType></li><li><xref:System.Windows.DataTemplate.%23ctor(System.Object)?displayProperty=nameWithType></li></ul>|
