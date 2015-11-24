# urho3d-post-process-dof

Usage:

```
#include "SmoothFocus.h"
    
MyApp(Context* context) :
     Application(context)
{
    SmoothFocus::RegisterObject(context);
}

void MyApp::Start()
{
    viewport = SharedPtr<Viewport>(new Viewport (context_, scene, camera));	
    viewport->SetRenderPath(cache->GetResource<XMLFile>("RenderPaths/ForwardHWDepthDOF.xml"));
    SmoothFocus* sf = camera->GetNode()->CreateComponent<SmoothFocus>();
    sf->SetViewport(viewport);
    sf->SetFocusTime(0.5f);
}
```
