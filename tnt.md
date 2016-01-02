//creates fake creeper explosion to scare players

package {$TopLevelDomain}.{$Domain}.{$TnT};
 
import org.bukkit.plugin.java.JavaPlugin;
 
public final class {$TnT} extends JavaPlugin {
@EventHandler
public void onExplosionPrime(ExplosionPrimeEvent event) {
    Entity entity = event.getEntity();
 
    // If the event is about primed TNT (TNT that is about to explode), then do something
    if (entity instanceof TNTPrimed) {
        entity.getWorld().createExplosion(entity.getLocation(), 0);
    }
}
