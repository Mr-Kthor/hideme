//lighting at looking point

package {$TopLevelDomain}.{$Domain}.{$LightEm};
 
import org.bukkit.plugin.java.JavaPlugin;
 
public final class {$LightEm} extends JavaPlugin {
@EventHandler
public void onPlayerInteractBlock(PlayerInteractEvent event) {
    Player player = event.getPlayer();
    if (player.getItemInHand().getType() == Material.FISHING_ROD) {
        // Creates a bolt of lightning at a given location. In this case, that location is where the player is looking.
        // Can only create lightning up to 200 blocks away.
        player.getWorld().strikeLightning(player.getTargetBlock((Set<Material>) null, 200).getLocation());
    }
}
